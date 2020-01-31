---
title: Operações e funções - Técnicas Q# Microsoft Docs
description: Operações e funções - Técnicas Q#
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820781"
---
# <a name="q-operations-and-functions"></a>Q# Operações e Funções

Os programas q# consistem em uma ou mais *operações* que descrevem os efeitos colaterais que as operações quânticas podem ter nos dados *quânticos,* e uma ou mais funções que permitem modificações a dados clássicos. Em contraste com as operações, as funções são usadas para descrever comportamentos puramente clássicos e não têm quaisquer efeitos além de calcular valores de saída clássicos.

Cada operação definida em Q# pode então chamar qualquer número de outras operações, incluindo as operações intrínsecas incorporadas definidas pela língua. A forma particular como estas operações intrínsecas são definidas depende da máquina-alvo. Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.

## <a name="defining-new-operations"></a>Definição de Novas Operações

Como descrito acima, o bloco de construção mais básico de um programa quântico escrito em Q# é uma *operação*, que pode ser chamada de aplicações clássicas .NET, por exemplo, usando um simulador, ou por outras operações dentro de Q#.
Cada operação tem uma entrada, produz uma saída e especifica a implementação para uma ou mais especializações de operação.
Por exemplo, a operação seguinte define apenas uma especialização corporal padrão e toma um único qubit como entrada, em seguida, chama a operação de `X` incorporada nessa entrada:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A palavra-chave `operation` inicia a definição de operação, e é seguida pelo nome; aqui, `BitFlip`.
Em seguida, o tipo de entrada é definido como `Qubit`, juntamente com um nome `target` por se referir à entrada dentro da nova operação.
Da mesma forma, o `Unit` define que a saída da operação está vazia.
Isto é usado da C# mesma forma que `void` em e F# outras línguas imperativas, e é equivalente a `unit` em e outras línguas funcionais.

> [!NOTE]
> Vamos explorar isto com mais detalhes abaixo, mas cada operação em Q# leva exatamente uma entrada e devolve exatamente uma saída.
> Várias inputs e saídas são então representadas usando *tuples,* que recolhem múltiplos valores juntos num único valor.
> Informalmente, dizemos que Q# é uma linguagem "tuple-in tuple-out".
> Seguindo este conceito, `()` deve ser lido como o tuple "vazio", que tem o tipo `Unit`.

No âmbito da nova operação, a implementação pode ser especificada diretamente na declaração se apenas a implementação da especialização do organismo predefinido tiver de ser especificada explicitamente. Além disso, é possível definir as implementações de, por exemplo, uma ou mais operações `functor`, tal como elaborada a seguir. No exemplo acima, a única declaração é chamar a operação Q# incorporada <xref:microsoft.quantum.intrinsic.x>.

As operações também podem devolver tipos mais interessantes do que `Unit`.
Por exemplo, a operação <xref:microsoft.quantum.intrinsic.m> devolve uma saída de tipo `Result`, representando ter efetuado uma medição. Podemos passar a saída de uma operação para outra operação, ou podemos usá-la com a palavra-chave `let` para definir uma nova variável.
<!-- Link to UID for superdense conceptual and example documentation. -->
Isto permite representar a computação clássica que interage com operações quânticas a um nível baixo, como na codificação superdensa:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Functors, adjoint e controlado
Se uma operação implementar uma transformação unitária, então é possível definir como a operação funciona quando *adjoint ou* *controlada*. Uma especialização adjoint de uma operação especifica como age quando é executada ao contrário, enquanto uma especialização controlada especifica como uma operação funciona quando aplicada condicionada no estado de um registo quântico.
A existência destas especializações pode ser declarada como parte da assinatura da operação: `is Adj + Ctl` no seguinte exemplo. A implementação correspondente para cada especialização declarada implicitamente é então gerada pelo compilador. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Muitas operações em Q# representam portões unitários.
> Se $U$ é o portão unitário representado por uma operação `U`, então `Adjoint U` representa o portão unitário $U^\dagger$.

No caso de a implementação não poder ser gerada pelo compilador, pode ser explicitamente especificada. Tais declarações explícitas de especialização podem consistir numa diretiva de geração adequada ou numa aplicação definida pelo utilizador. O código em `PrepareEntangledPair` acima, por exemplo, equivale ao código abaixo contendo declarações explícitas de especialização: 

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
A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação da especialização.
Se o compilador não conseguir gerar automaticamente a implementação para uma determinada especialização, ou se uma implementação mais eficiente puder ser administrada, então a implementação também pode ser definida manualmente.

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
No exemplo acima, `adjoint invert;` indica que a especialização adjoint deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjoint controlada deve ser gerada invertendo a implementação da especialização controlada.

Veremos mais exemplos disso no Fluxo de [Controlo de Ordem Superior.](xref:microsoft.quantum.concepts.control-flow)

Para chamar uma especialização de uma operação, utilize as palavras-chave `Adjoint` ou `Controlled`.
Por exemplo, o exemplo de codificação superdense acima pode ser escrito mais compactamente usando a adjoint de `PrepareEntangledPair` para transformar o estado emaranhado de volta em um par de qubits sem emaranhado:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Há uma série de limitações importantes a ter em conta na conceção de operações de utilização com functors.
Mais criticamente, as especializações para uma operação que utilize o valor de saída de qualquer outra operação não podem ser geradas automaticamente pelo compilador, uma vez que é ambígua como reordenar as declarações numa operação deste tipo para obter o mesmo efeito.


## <a name="defining-new-functions"></a>Definição de novas funções

Q# também permite definir funções , que são distintas das *operações*na medida em que não são permitidas a ter quaisquer efeitos além do cálculo de um valor de saída.
Em particular, as funções não podem ligar para operações, agir sobre qubits, amostrar números aleatórios, ou depender de qualquer estado para além do valor de entrada para uma função.
Como consequência, as funções Q# são *puras,* na medida em que sempre mapeiam os mesmos valores de entrada para os mesmos valores de saída.
Isto permite ao compilador Q# reordenar com segurança como e quando as funções são chamadas ao gerar especializações de operação.

A definição de uma função funciona da mesma forma para definir uma operação, exceto que nenhuma especialização adjoint ou controlada pode ser definida para uma função.
Por exemplo:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Sempre que é possível fazê-lo, é útil escrever a lógica clássica em termos de funções e não de operações, para que possa ser mais facilmente utilizada a partir de dentro das operações.
Se tivéssemos escrito `Square` como operação, por exemplo, o compilador não teria sido capaz de garantir que chamá-lo com a mesma entrada produziria consistentemente as mesmas saídas.

Para sublinhar a diferença entre funções e operações, considere o problema da amostragem clássica de um número aleatório de dentro de uma operação Q#:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

De cada vez que se chama `U`, terá uma ação diferente sobre `target`.
Em particular, o compilador não pode garantir que, se adicionássemos uma declaração de especialização `adjoint auto` a `U`, então `U(target); Adjoint U(target);` atua como identidade (isto é, como uma não-operação).
Isto viola a definição da adjoint que vimos em [Vetores e Matrizes](xref:microsoft.quantum.concepts.vectors), de tal forma que permitir gerar automaticamente uma especialização adjoint numa operação em que chamámos a operação <xref:microsoft.quantum.math.randomreal> quebraria as garantias fornecidas pelo compilador; <xref:microsoft.quantum.math.randomreal> é uma operação para a qual não existe nenhuma versão adjoint ou controlada.

Por outro lado, permitir chamadas de funções como `Square` é segura, na medida em que o compilador pode ter a certeza de que só precisa de preservar a entrada para `Square`, a fim de manter a sua produção estável.
Assim, isolar o máximo de lógica clássica possível em funções facilita a reutilização dessa lógica em outras funções e operações.

## <a name="control-flow"></a>Fluxo de Controlo

Dentro de uma operação ou função, cada declaração executa por ordem, semelhante às línguas clássicas mais comuns imperativas.
No entanto, este fluxo de controlo pode ser modificado de três formas distintas:

- `if` Declarações
- `for` Loops
- `repeat`-`until` Loops

Adiamos a discussão deste último até discutirmos os circuitos [Repeat Until Success (RUS).](xref:microsoft.quantum.techniques.qubits#measurements)
No entanto, as construções de fluxo de `if` e `for` de controlo prosseguem num sentido familiar para a maioria das línguas clássicas de programação.
Em especial, uma declaração `if` pode tomar uma condição, pode ser seguida por uma ou mais declarações `elif`, podendo terminar com um `else`:

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

Da mesma forma, `for` loops indicam iteração sobre uma gama de inteiros ou sobre os elementos de uma matriz:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

É importante `for` loops e `if` declarações podem mesmo ser utilizados em operações para as quais as especializações são geradas automaticamente. Nesse caso, a adjoint de um laço de `for` inverte a direção e toma a adjoint de cada iteração.
Isto segue o princípio dos "sapatos e meias": se quiser desfazer a colocação de meias e depois sapatos, tem de desfazer calçar sapatos e depois desfazer calças.
Funciona decididamente menos bem para tentar tirar as meias enquanto ainda usa os sapatos!

## <a name="operations-and-functions-as-first-class-values"></a>Operações e Funções como Valores de Primeira Classe

Uma técnica crítica para o raciocínio sobre o fluxo de controlo e a lógica clássica usando funções em vez de operações é utilizar que as operações e funções em Q# são *de primeira classe*.
Ou seja, são cada valores da língua por direito próprio.
Por exemplo, o seguinte é perfeitamente válido código Q#, se um pouco indireto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

O valor da variável `ourH` no corte acima é então a operação <xref:microsoft.quantum.intrinsic.h>, de modo a que possamos chamar esse valor como qualquer outra operação.
Isto permite-nos escrever operações que tomam as operações como parte da sua entrada, formando conceitos de fluxo de controlo de maior ordem.
Por exemplo, podemos imaginar querer "quadrar" uma operação aplicando-a duas vezes ao mesmo qubit alvo.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

Neste exemplo, a seta `=>` que aparece no tipo `(Qubit => Unit)` denota que o campo de entrada `op` é uma operação que toma como entrada o tipo `Qubit` e produz uma tuple vazia como sua saída.
Além disso, especificamos as características desse tipo de operação, que contêm as informações sobre as quais os functores são suportados.
Uma operação de tipo `(Qubit => Unit)` não suporta nem o `Adjoint` nem o functor `Controlled`. Se quisermos indicar que uma operação desse tipo tem de suportar, por exemplo, o functor `Adjoint`, temos de o declarar como sendo adjointable. Isto é feito utilizando a anotação `is Adj` ao tipo. Da mesma forma, `(Qubit => Unit is Ctl)` denota que uma operação deste tipo suporta o functor `Controlled`. Vamos explorar isto ainda mais quando discutirmos [tipos em Q#] (xref:microsoft.quantum.language.type-model) de uma forma mais geral.

Por enquanto, sublinhamos que também podemos devolver as operações como parte de saídas, de modo a podermos isolar alguns tipos de lógica condicional clássica como função clássica que devolve uma descrição de um programa quântico sob a forma de uma operação.
Como exemplo simples, considere o exemplo da teletransporte, em que o partido que recebe uma mensagem clássica de dois bits precisa de usar a mensagem para descodificar o seu qubit no estado teletransportado adequado.
Poderíamos escrever isto em termos de uma função que pega nessas duas partes clássicas e devolve a operação de descodificação adequada.

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

Esta nova função é, de facto, uma função, na forma de a chamarmos com os mesmos valores de `hereBit` e `thereBit`, teremos sempre de volta a mesma operação.
Assim, o descodificador pode ser executado com segurança dentro de operações sem ter de raciocinar sobre como a lógica de descodificação interage com as definições das diferentes especializações de operação.
Ou seja, isolamos a lógica clássica dentro de uma função, garantindo ao compilador que a chamada de função pode ser reordenada impunemente enquanto a entrada for preservada.

Também podemos tratar as funções como valores de primeira classe, como veremos mais detalhadamente quando discutirmos os tipos de [operações e funções.](#operations-and-functions-as-first-class-values)

## <a name="partially-applying-operations-and-functions"></a>Aplicação parcial de operações e funções

Podemos fazer significativamente mais com funções que devolvem as operações utilizando *aplicações parciais,* nas quais podemos fornecer uma ou mais partes da entrada a uma função ou operação sem realmente chamá-lo. Por exemplo, recordando o exemplo `ApplyTwice` acima, podemos indicar que não queremos especificar, imediatamente, a que qubit a operação de entrada deve aplicar:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Neste caso, a variável local `twiceOp` detém a operação parcialmente aplicada `ApplyTwice(op, _)`, onde partes da entrada que ainda não foram especificadas são indicadas por `_`.
Quando realmente chamamos `twiceOp` na linha seguinte, passamos como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.
Assim, o corte acima é efetivamente idêntico ao de ter chamado `ApplyTwice(op, target)` diretamente, salvo para isso introduzimos uma nova variável local que nos permite atrasar a chamada, fornecendo algumas partes da entrada.

Uma vez que uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, podemos aplicar parcialmente as operações mesmo a partir de funções.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Em princípio, a lógica clássica dentro `SquareOperation` poderia ter sido muito mais envolvida, mas continua isolada do resto de uma operação pelas garantias que o compilador pode oferecer sobre funções.
Esta abordagem será usada em toda a biblioteca padrão Q# para expressar o fluxo de controlo clássico de uma forma que pode ser facilmente usada dentro de programas quânticos.
