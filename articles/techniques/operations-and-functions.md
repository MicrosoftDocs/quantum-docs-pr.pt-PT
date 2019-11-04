---
title: 'Q # técnicas-operações e funções | Microsoft Docs'
description: 'Técnicas de Q # – operações e funções'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 06da09dc9c6e0ba0331db6bc0cd3d2ddeb287113
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183459"
---
# <a name="q-operations-and-functions"></a>Operações e funções do Q #

Os programas de Q # consistem em uma ou mais *operações* que descrevem os efeitos colaterais que as operações Quantum podem ter em dados Quantum e uma ou mais *funções* que permitem modificações em dados clássicos. Em contraste com as operações, as funções são usadas para descrever o comportamento puramente clássico e não têm nenhum efeito além de calcular os valores de saída clássicas.

Cada operação definida em Q # pode então chamar qualquer número de outras operações, incluindo as operações intrínsecas internas definidas pelo idioma. A maneira específica em que essas operações intrínsecas são definidas depende da máquina de destino. Quando compilada, cada operação é representada como um tipo de classe do .NET que pode ser fornecido para os computadores de destino.

## <a name="defining-new-operations"></a>Definindo novas operações

Conforme descrito acima, o bloco de construção mais básico de um programa Quantum escrito em Q # é uma *operação*, que pode ser chamada a partir de aplicativos .net clássicos, por exemplo, usando um simulador ou por outras operações em Q #.
Cada operação usa uma entrada, produz uma saída e especifica a implementação para uma ou mais especializações de operação.
Por exemplo, a operação a seguir define apenas uma especialização de corpo padrão e usa um único qubit como sua entrada e, em seguida, chama a operação de `X` interna nessa entrada:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A palavra-chave `operation` começa a definição da operação e é seguida pelo nome; aqui, `BitFlip`.
Em seguida, o tipo da entrada é definido como `Qubit`, juntamente com um nome `target` para fazer referência à entrada dentro da nova operação.
Da mesma forma, a `Unit` define que a saída da operação está vazia.
Isso é usado da mesma forma para C# `void` e outras linguagens imperativas e é equivalente a F# `unit` no e outras linguagens funcionais.

> [!NOTE]
> Exploraremos isso mais detalhadamente abaixo, mas cada operação em Q # usa exatamente uma entrada e retorna exatamente uma saída.
> Várias entradas e saídas são representadas usando *tuplas*, que coletam vários valores juntos em um único valor.
> Informalmente, dizemos que Q # é uma linguagem de "tupla na tupla".
> Seguindo esse conceito, `()` deve ser lido como a tupla "Empty", que tem o tipo `Unit`.

Na nova operação, a implementação pode ser especificada diretamente na declaração se apenas a implementação da especialização de corpo padrão precisar ser especificada explicitamente. Além disso, é possível definir as implementações de, por exemplo, uma ou mais operações de `functor`, conforme elaborado abaixo. No exemplo acima, a única instrução é chamar a operação interna Q # <xref:microsoft.quantum.intrinsic.x>.

As operações também podem retornar tipos mais interessantes do que `Unit`.
Por exemplo, a operação <xref:microsoft.quantum.intrinsic.m> retorna uma saída do tipo `Result`, representando tendo realizado uma medição. Podemos passar a saída de uma operação para outra operação ou pode usá-la com a palavra-chave `let` para definir uma nova variável.
<!-- Link to UID for superdense conceptual and example documentation. -->
Isso permite representar a computação clássica que interage com as operações Quantum em um nível baixo, como na codificação superdensa:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Transmissão functors, adjoine e controlado
Se uma operação implementar uma transformação unitário, será possível definir como a operação age quando *adjointed* ou *controlada*. Uma especialização adjacente de uma operação especifica como ela funciona quando executada em ordem inversa, enquanto uma especialização controlada especifica como uma operação age quando aplicada com condição no estado de um registro Quantum.
A existência dessas especializações pode ser declarada como parte da assinatura da operação: `is Adj + Ctl` no exemplo a seguir. A implementação correspondente para cada tal especialização declarada implicitamente é gerada pelo compilador. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Muitas operações em Q # representam Gates unitários.
> Se $U $ é o portão unitário representado por uma operação `U`, `Adjoint U` representa o portão unitário $U ^ \dagger $.

No caso em que a implementação não pode ser gerada pelo compilador, ela pode ser especificada explicitamente. Essas declarações de especialização explícitas podem consistir em uma diretiva de geração adequada ou em uma implementação definida pelo usuário. O código em `PrepareEntangledPair` acima, por exemplo, é equivalente ao código abaixo que contém declarações de especialização explícitas: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação de especialização.
Se o compilador não puder gerar a implementação para determinada especialização automaticamente ou se uma implementação mais eficiente puder ser fornecida, a implementação também poderá ser definida manualmente.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
No exemplo acima, `adjoint invert;` indica que a especialização de adjacente deve ser gerada ao inverter a implementação do corpo e `controlled adjoint invert;` indica que a especialização adjacente controlada deve ser gerada por meio da inversão da implementação fornecida do especialização controlada.

Veremos mais exemplos disso no fluxo de [controle de ordem superior](xref:microsoft.quantum.concepts.control-flow).

Para chamar uma especialização de uma operação, use as palavras-chave `Adjoint` ou `Controlled`.
Por exemplo, o exemplo de codificação superdensar acima pode ser escrito mais compactamente usando o `PrepareEntangledPair` de código para transformar o estado confusas de volta em um par unentangled de qubits:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Há várias limitações importantes a serem consideradas ao criar operações para uso com o transmissão functors.
O mais importante é que as especializações para uma operação que usa o valor de saída de qualquer outra operação não podem ser geradas automaticamente pelo compilador, pois é ambígua como reordenar as instruções nessa operação para obter o mesmo efeito.


## <a name="defining-new-functions"></a>Definindo novas funções

O Q # também permite definir *funções*, que são diferentes das operações, pois não têm permissão para ter nenhum efeito além de calcular um valor de saída.
Em particular, as funções não podem chamar operações, agir em qubits, números aleatórios de exemplo ou depender de outro Estado além do valor de entrada para uma função.
Como consequência, as funções Q # são *puras*, pois elas sempre mapeiam os mesmos valores de entrada para os mesmos valores de saída.
Isso permite que o compilador Q # reordene com segurança como e quando as funções são chamadas ao gerar especializações de operação.

A definição de uma função funciona de forma semelhante à definição de uma operação, exceto que nenhuma especialização adjacente ou controlada pode ser definida para uma função.
Por exemplo:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Sempre que for possível fazer isso, é útil escrever a lógica clássica em termos de funções em vez de operações, para que ela possa ser usada mais prontamente em operações.
Se tivéssemos escrito `Square` como uma operação, por exemplo, o compilador não teria conseguido garantir que chamá-lo com a mesma entrada produzirá consistentemente as mesmas saídas.

Para enfatizar a diferença entre funções e operações, considere o problema de amostragem clássica de um número aleatório de dentro de uma operação Q #:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Cada vez que `U` for chamado, ele terá uma ação diferente em `target`.
Em particular, o compilador não pode garantir que, se adicionamos uma declaração de especialização de `adjoint auto` para `U`, `U(target); Adjoint U(target);` atua como identidade (ou seja, como não operacional).
Isso viola a definição do adjoin que vimos em [vetores e matrizes](xref:microsoft.quantum.concepts.vectors), de modo que permitir a geração automática de uma especialização adjacente em uma operação em que chamamos a operação <xref:microsoft.quantum.math.randomreal> interromperia as garantias fornecidas pelo compilador ; <xref:microsoft.quantum.math.randomreal> é uma operação para a qual não existe nenhuma versão adjacente ou controlada.

Por outro lado, permitir chamadas de função como `Square` é seguro, pois o compilador pode ter certeza de que ele só precisa preservar a entrada para `Square` para manter sua saída estável.
Portanto, isolar o máximo de lógica clássica possível em funções facilita a reutilização dessa lógica em outras funções e operações semelhantes.

## <a name="control-flow"></a>Fluxo de Controlo

Em uma operação ou função, cada instrução é executada em ordem, semelhante às linguagens clássicas mais comuns.
No entanto, esse fluxo de controle pode ser modificado de três maneiras distintas:

- Instruções de `if`
- Loops de `for`
- `repeat`-loops de `until`

Adiamos a discussão do segundo até discutirmos a [repetição até que os circuitos de sucesso (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) .
No entanto, as construções de fluxo de controle `if` e `for`, no entanto, prosseguem de forma familiar com a maioria das linguagens de programação clássicas.
Em particular, uma instrução `if` pode tomar uma condição, pode ser seguida por uma ou mais instruções `elif` e pode terminar com uma `else`:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

Da mesma forma, `for` loops indicam a iteração em um intervalo de inteiros ou sobre os elementos de uma matriz:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Importante, `for` loops e instruções de `if` podem até ser usados em operações para as quais as especializações são geradas automaticamente. Nesse caso, o adjoin de um loop de `for` inverte a direção e leva o adjacente de cada iteração.
Isso segue o princípio "sapatos-and-Socks": se você deseja desfazer a colocação em SOCKS e, em seguida, os sapatos, você deve desfazer a colocação de sapatos e, em seguida, desfazer a colocação em Socks.
Ele funciona decididamente menos bem para tentar e retomar seus Socks enquanto você ainda estiver aproveitando seus sapatos!

## <a name="operations-and-functions-as-first-class-values"></a>Operações e funções como valores de primeira classe

Uma técnica crítica para o raciocínio sobre o fluxo de controle e a lógica clássica usando funções em vez de operações é utilizar essas operações e funções em Q # são de *primeira classe*.
Ou seja, eles são cada um dos valores no idioma que estão no seu próprio direito.
Por exemplo, este é um código Q # perfeitamente válido, se um pouco indireto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

O valor da variável `ourH` no trecho acima é, então, a operação <xref:microsoft.quantum.intrinsic.h>, de modo que possamos chamar esse valor como qualquer outra operação.
Isso nos permite escrever operações que usam operações como parte de sua entrada, formando conceitos de fluxo de controle de ordem mais alta.
Por exemplo, podemos imaginar que queira "quadrado" uma operação aplicando-a duas vezes ao mesmo qubit de destino.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

Neste exemplo, a `=>` seta exibida no tipo `(Qubit => Unit)` denota que o campo de entrada `op` é uma operação que usa como entrada o tipo `Qubit` e produz uma tupla vazia como sua saída.
Além disso, especificamos as características desse tipo de operação, que contêm as informações sobre quais transmissão functors têm suporte.
Uma operação do tipo `(Qubit => Unit)` não dá suporte aos `Adjoint` nem ao `Controlled` functor. Se quisermos indicar que uma operação desse tipo deve dar suporte, por exemplo, a `Adjoint` functor, precisamos declará-la como sendo de adjointable. Isso é feito usando a anotação `is Adj` para o tipo. Da mesma forma, `(Qubit => Unit is Ctl)` denota que uma operação desse tipo dá suporte ao `Controlled` functor. Exploraremos isso ainda mais quando discutimos [Types in Q #] (xref: Microsoft. Quantum. Language. Type-Model) mais geralmente.

Por enquanto, enfatizamos que também podemos retornar operações como parte das saídas, de modo que possamos isolar alguns tipos de lógica condicional clássica como uma função clássica que retorna uma descrição de um programa Quantum na forma de uma operação.
Como exemplo simples, considere o exemplo de teleportação, no qual a parte que recebe uma mensagem clássica de dois bits precisa usar a mensagem para decodificar seu qubit no estado de Teleporta adequado.
Poderíamos escrever isso em termos de uma função que pega esses dois bits clássicos e retorna a operação de decodificação adequada.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Essa nova função é realmente uma função, já que, se o chamarmos com os mesmos valores de `hereBit` e `thereBit`, sempre obteremos a mesma operação.
Assim, o decodificador pode ser executado com segurança dentro de operações sem ter que ter por motivo de como a lógica de decodificação interage com as definições das diferentes especializações de operação.
Ou seja, isolamos a lógica clássica dentro de uma função, garantindo ao compilador que a chamada de função pode ser reordenada com impunity, desde que a entrada seja preservada.

Também podemos tratar funções como valores de primeira classe, como veremos mais detalhadamente quando discutimos [as operações e os tipos de função](#operations-and-functions-as-first-class-values).

## <a name="partially-applying-operations-and-functions"></a>Aplicação parcial de operações e funções

Podemos fazer significativamente mais com funções que retornam operações usando o *aplicativo parcial*, no qual podemos fornecer uma ou mais partes da entrada a uma função ou operação sem realmente chamá-la. Por exemplo, rechamar o exemplo de `ApplyTwice` acima, podemos indicar que não queremos especificar, imediatamente, a qual qubit a operação de entrada deve ser aplicada:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Nesse caso, a variável local `twiceOp` mantém a operação parcialmente aplicada `ApplyTwice(op, _)`, em que partes da entrada que ainda não foram especificadas são indicadas por `_`.
Quando realmente chamamos `twiceOp` na próxima linha, passamos como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.
Assim, o trecho acima é efetivamente idêntico a ter chamado `ApplyTwice(op, target)` diretamente, salvar para que tenhamos introduzido uma nova variável local que nos permite atrasar a chamada enquanto fornece algumas partes da entrada.

Como uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, podemos aplicar operações parcialmente de forma segura, mesmo a partir de funções.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Em princípio, a lógica clássica dentro de `SquareOperation` poderia ter sido muito mais envolvida, mas ainda é isolada do restante de uma operação pelas garantias que o compilador pode oferecer sobre as funções.
Essa abordagem será usada em toda a biblioteca padrão de Q # para expressar o fluxo de controle clássico de forma que possa ser prontamente usada em programas Quantum.
