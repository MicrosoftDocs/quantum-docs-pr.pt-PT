---
title: Operações e funções em Q#
description: Como definir e chamar operações e funções, bem como as especializações de operação controladas e adjacentes.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55e6d3e1a242386c46213083692377520df83a80
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692134"
---
# <a name="operations-and-functions-in-no-locq"></a>Operações e Funções em Q#

## <a name="defining-new-operations"></a>Definição de Novas Operações

As operações são o núcleo Q# de.
Uma vez declarados, podem ser chamados a partir de aplicações clássicas .NET, por exemplo, utilizando um simulador ou por outras operações no seu interior Q# .
Cada operação definida Q# pode chamar qualquer número de outras operações, incluindo as operações intrínsecas incorporadas definidas pela língua. A forma particular como Q# define estas operações intrínsecas depende da máquina-alvo.
Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.

Cada Q# ficheiro de origem pode definir qualquer número de operações.
Os nomes de operação devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de tipo ou função.

Uma declaração de operação consiste na palavra-chave, `operation` seguida do símbolo que é o nome da operação, um tuple identificador dactilografado que define os argumentos para a operação, um `:` cólon, um tipo de anotação que descreve o tipo de resultado da operação, opcionalmente uma anotação com as características de funcionamento, uma cinta aberta e, em seguida, o corpo da declaração de operação, em `{ }` anexo.

Cada operação leva uma entrada, produz uma saída, e especifica a implementação para uma ou mais especializações de operação.
As possíveis especializações, e como defini-las e chamá-las, são detalhadas nas diferentes secções deste artigo.
Por enquanto, considere a seguinte operação, que define apenas uma especialização do corpo predefinido e toma um único qubit como sua entrada, em seguida, chama a operação incorporada <xref:Microsoft.Quantum.Intrinsic.X> nessa entrada:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A palavra-chave `operation` começa a definição de operação, seguida do nome; aqui, `BitFlip` .
Em seguida, o tipo de entrada é definido `Qubit` (), juntamente com um nome, `target` para se referir à entrada dentro da nova operação.
Por último, `Unit` define que a saída da operação está vazia.
`Unit` é usado da mesma forma `void` em C# e outras línguas imperativas e é equivalente `unit` a em F# e outras línguas funcionais.

As operações também podem devolver tipos mais interessantes do que `Unit` .
Por exemplo, a <xref:Microsoft.Quantum.Intrinsic.m> operação devolve uma saída do `Result` tipo, representando ter efetuado uma medição.  Pode passá-lo de uma operação para outra operação ou usá-la com a `let` palavra-chave para definir uma nova variável.

Esta abordagem permite representar a computação clássica que interage com operações quânticas a um nível baixo, como na [codificação superdense:](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Cada operação Q# requer exatamente uma entrada e devolve exatamente uma saída.
> Várias entradas e saídas são representadas usando *tuples,* que recolhem múltiplos valores juntos num único valor.
> A este respeito, Q# é uma linguagem "tuple-in tuple-out".
> Seguindo este conceito, um conjunto de parênteses vazios, `()` deve então ser lido como o tuple "vazio", que tem o tipo `Unit` .

## <a name="controlled-and-adjoint-operations"></a>Operações controladas e adjacentes

Se uma operação implementar uma transformação unitária, como é o caso de muitas operações em Q# , então é possível definir como a operação age quando *contígua* ou *controlada* . Uma especialização *adjacente* de uma operação especifica como o "inverso" da operação atua, enquanto uma especialização *controlada* especifica como uma operação age quando a sua aplicação está condicionada ao estado de um determinado registo quântico.

Os contíguos das operações quânticas são cruciais para muitos aspetos da computação quântica. Para um exemplo de uma dessas situações discutidas ao lado de uma técnica de Q# programação útil, ver [Control Flow: Conjugações](xref:microsoft.quantum.guide.controlflow#conjugations). A versão controlada de uma operação é uma nova operação que aplica efetivamente a operação base apenas se todos os qubits de controlo estiverem num estado especificado.
Se os qubits de controlo estiverem em sobreposição, então a operação de base é aplicada de forma coerente à parte apropriada da sobreposição.
Assim, as operações controladas são frequentemente usadas para gerar emaranhados.

Naturalmente, também poderia existir uma especialização *adjacente controlada,* especificando a aplicação controlada do adjacente de uma operação.

> [!NOTE]
> Se $U$ é a transformação unitária implementada por uma `U` operação, então `Adjoint U` representa a transformação unitária $U^\dagger$, que é a transposição conjugada complexa.
> Aplicar sucessivamente uma operação e, em seguida, o seu contíguo a um estado deixa o estado inalterado, como ilustrado pelo facto de $UU^\dagger = U^\dagger U = \id$, a matriz de identidade.
> A representação unitária de uma operação controlada é um pouco mais matizada, mas pode encontrar mais detalhes em [conceitos de computação quântica: múltiplos qubits](xref:microsoft.quantum.concepts.multiple-qubits).

A secção seguinte descreve como chamar estas várias especializações no seu Q# código e como definir operações para as suportar.

### <a name="calling-operation-specializations"></a>Especializações de operação de chamada

Um *functor* Q# é uma fábrica que define uma nova operação a partir de outra operação.
Os dois funtores padrão Q# são `Adjoint` `Controlled` e.

Os funtores têm acesso à implementação da operação base ao definir a implementação da nova operação.
Assim, os funtores podem desempenhar funções mais complexas do que as funções tradicionais de alto nível. Os functors não têm representação no Q# sistema de tipo. Não é, portanto, atualmente possível ligá-los a uma variável ou passá-las como argumentos. 

Use um functor aplicando-o a uma operação, que devolve uma nova operação.
Por exemplo, a aplicação do `Adjoint` functor à `Y` operação devolve a nova operação `Adjoint Y` . Pode invocar a nova operação como qualquer outra operação.
Para uma operação de apoio à aplicação dos `Adjoint` `Controlled` ou funtores, o seu tipo de devolução tem necessariamente de ser `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint` functor

Assim, `Adjoint Y(q1)` aplica o `Adjoint` functor à `Y` operação para gerar uma nova operação, e aplica essa nova operação a `q1` .
A nova operação tem a mesma assinatura e tipo que a operação `Y` base.
Em particular, a nova operação também apoia `Adjoint` , e suporta se e só se a `Controlled` operação de base o fez.
O `Adjoint` functor é o seu próprio inverso; ou seja, é sempre o mesmo que `Adjoint Adjoint Op` `Op` .

#### <a name="controlled-functor"></a>`Controlled` functor

Da mesma forma, `Controlled X(controls, target)` aplica o `Controlled` functor à `X` operação para gerar uma nova operação, e aplica essa nova operação a `controls` e `target` .

> [!NOTE]
> Em Q# , versões controladas sempre tomam uma série de qubits de controlo, e o controlo é sempre baseado em todos os qubits de controlo que estão no estado computacional `PauliZ` , `One` $\ket {1} $.
> O controlo baseado noutros Estados é conseguido aplicando a operação unitária adequada aos qubits de controlo antes da operação controlada e, em seguida, aplicando os inversos da operação unitária após a operação controlada.
> Por exemplo, aplicar uma `X` operação a um qubit de controlo antes e depois de uma operação controlada faz com que a `Zero` operação controle o estado ($\ket {0} $) para esse qubit; aplicando uma `H` operação antes e depois dos controlos sobre o `PauliX` `One` estado, ou seja , -1 egenvalue de Pauli X, $\ket {-} \mathrel{:=} (\ket {0} - \ket {1} ) / \sqrt {2} $ em vez do `PauliZ` `One` estado.

Dada a expressão de operação, pode formar uma nova expressão de operação utilizando o `Controlled` functor.
A assinatura da nova operação baseia-se na assinatura da operação original.
O tipo de resultado é o mesmo, mas o tipo de entrada é um dois tuple com uma matriz qubit que mantém o(s) qubit de controlo como primeiro elemento e os argumentos da operação original como segundo elemento.
A nova operação suporta `Controlled` , e irá suportar se e `Adjoint` somente se a operação original o fizer.

Se a operação original teve apenas um argumento, então [a equivalência de tuple singleton](xref:microsoft.quantum.guide.types) entra em jogo aqui.
Por exemplo, `Controlled X` é a versão controlada da `X` operação. 
`X` tem `(Qubit => Unit is Adj + Ctl)` tipo, assim `Controlled X` tem `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` tipo; por causa da equivalência de tuple singleton, este é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Se a operação base levou vários argumentos, lembre-se de incluir os argumentos correspondentes da versão controlada da operação em parênteses para convertê-los em tuple.
Por exemplo, `Controlled Rz` é a versão controlada da `Rz` operação. 
`Rz` tem `((Double, Qubit) => Unit is Adj + Ctl)` tipo, assim `Controlled Rz` como o tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Assim, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (note os parênteses em torno `0.1, target` de ).

Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)` . Se um alvo deve ser controlado por dois qubits de controlo (CCNOT), utilize uma `Controlled X([control1, control2], target)` declaração.

#### `Controlled Adjoint` 

Os `Controlled` `Adjoint` funtores e funtores viajam, por isso não há diferença entre a aplicação `Controlled Adjoint Op` ou `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definição de implementações controladas e adjacentes

Na primeira declaração de operação nos exemplos anteriores, as operações `BitFlip` `DecodeSuperdense` foram definidas com assinaturas `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` e, respectivamente.
Tal como `DecodeSuperdense` as medições, não se trata de uma operação unitária e, portanto, não podem existir especializações não adjacentes controladas (recorde-se a exigência de tal operação `Unit` de devolução).
No entanto, como `BitFlip` simplesmente executa a operação unitária, <xref:Microsoft.Quantum.Intrinsic.X> poderia tê-lo definido com ambas as especializações.

Esta secção detalha como incluir a existência de especializações nas suas declarações de Q# operação, dando-lhes assim a capacidade de chamar em conjunto com os `Adjoint` ou `Controlled` funtores.
Para obter mais informações sobre algumas das situações em que é válido ou não é válido declarar determinadas especializações, consulte [Circunstâncias para definir validamente as especializações](#circumstances-for-validly-defining-specializations) neste artigo.

As características de operação definem que tipos de funtores pode aplicar à operação declarada e que efeito têm. A existência destas especializações pode ser declarada como parte da assinatura da operação, nomeadamente através de uma anotação com as características de funcionamento: `is Adj` `is Ctl` ou, ou `is Adj + Ctl` .
A implementação real de cada especialização pode ser *definida implicitamente* ou *explicitamente.*

### <a name="implicitly-specifying-implementations"></a>Especificar implicitamente implementações

Neste caso, o corpo da declaração de operação consiste exclusivamente na implementação por defeito. Por exemplo:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
Aqui, a implementação correspondente para cada uma dessas especializações implicitamente declaradas é gerada automaticamente pelo compilador, a ser realizada se os `Adjoint` `Controlled` ou funtores forem utilizados.

Assim, uma chamada de `Adjoint PrepareEntangledPair` resultaria na implementação do compilador adjacente `CNOT` e, em seguida, do adjacente de `H` .
Estas operações individuais são ambas auto-adjacentes, pelo que a operação resultante `Adjoint PrepareEntangledPair` consistiria simplesmente em aplicar `CNOT(here, there)` e, em `H(here)` seguida, .
Assim, pode usar isto para escrever `DecodeSuperdense` o exemplo anterior de forma mais compacta, utilizando o adjacente de transformar o estado emaranhado de volta num par de `PrepareEntangledPair` qubits não emaranhados:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

A anotação com as características de funcionamento na declaração é útil para garantir que o compilador gera automaticamente outras especializações com base na implementação padrão. 

Existem várias limitações importantes a considerar ao conceber operações para uso com funtores.
Mais criticamente, as especializações para uma operação que utiliza o valor de saída de qualquer outra operação *não podem* ser geradas automaticamente pelo compilador, uma vez que é ambíguo como reordenar as declarações de tal operação para obter o mesmo efeito.

Por conseguinte, muitas vezes é útil especificar explicitamente as várias implementações.

### <a name="explicitly-specifying-implementations"></a>Especificar explicitamente implementações

No caso de o compilador não conseguir gerar a implementação, pode especirá-la explicitamente. Tais declarações explícitas de especialização podem consistir numa diretiva de *geração* adequada ou numa implementação definida pelo utilizador.
Seguem-se toda a gama de possibilidades, com alguns exemplos de especialização explícita. 


#### <a name="explicit-specialization-declarations"></a>Declarações explícitas de especialização

Q# As operações podem conter as seguintes declarações explícitas de especialização:

- A `body` especialização especifica a implementação da operação sem funtores aplicados.
- A `adjoint` especialização especifica a implementação da operação com o `Adjoint` functor aplicado.
- A `controlled` especialização especifica a implementação da operação com o `Controlled` functor aplicado.
- A `controlled adjoint` especialização especifica a implementação da operação com os `Adjoint` funtores e `Controlled` funtores aplicados.
  Esta especialização também pode ser `adjoint controlled` nomeada, uma vez que os dois funtores viajam.


Uma especialização de operação consiste na etiqueta de especialização (por exemplo, `body` `adjoint` ou) seguida de um dos seguintes:

- Uma declaração explícita, tal como descrita no seguinte.
- Uma *diretiva* que diz ao compilador *como* gerar a especialização, uma das seguintes:
  - `intrinsic`, o que indica que a máquina-alvo fornece a especialização.
  - `distribute`, usado com as `controlled` `controlled adjoint` especializações.
    Quando utilizado `controlled` com , indica que o compilador deve calcular a especialização aplicando-se a todas as `Controlled` operações no `body` .
    Quando utilizado `controlled adjoint` com , indica que o compilador deve calcular a especialização aplicando-se a todas as `Controlled` operações da `adjoint` especialização.
  - `invert`, o que indica que o compilador deve calcular a `adjoint` especialização invertendo a `body` , por exemplo, invertendo a ordem de operações e aplicando o adjacente a cada um.
    Quando `adjoint controlled` utilizado, isto indica que o compilador deve calcular a especialização invertendo a `controlled` especialização.
  - `self`, para indicar que a especialização adjacente é a mesma que a `body` especialização.
    A utilização `self` é legal para as `adjoint` `adjoint controlled` especializações.
    Pois, `adjoint controlled` `self` implica que a `adjoint controlled` especialização é a mesma que a `controlled` especialização.
  - `auto`, para indicar que o compilador deve selecionar uma diretiva adequada a aplicar.
    Não pode usar `auto` para a `body` especialização.

As diretivas e `auto` todos requerem um fecho do ponto de souco. `;`
A `auto` diretiva resolve a seguinte diretiva gerada se for fornecida uma declaração `body` explícita:

- A `adjoint` especialização gera de acordo com a `invert` diretiva.
- A `controlled` especialização gera de acordo com a `distribute` diretiva.
- A `adjoint controlled` especialização gera de acordo com a diretiva `invert` se for dada uma declaração `controlled` explícita, mas não uma para , e não para `adjoint` `distribute` outras.

> [!TIP]   
> Se uma operação for auto-adjacente, especifique explicitamente a especialização adjacente ou a especialização adjacente controlada através da diretiva `self` de geração, a fim de permitir que o compilador utilize essa informação para fins de otimização.

Uma declaração de especialização contendo uma implementação definida pelo utilizador consiste num tuple de argumento seguido de um bloco de declaração com o Q# código que implementa a especialização.
Na lista de argumentos, `...` é usado para representar os argumentos declarados para a operação como um todo.
Para `body` `adjoint` e, a lista de argumentos deve ser `(...)` sempre; para `controlled` `adjoint controlled` e, a lista de argumentos deve ser um símbolo que represente a matriz de qubits de controlo, seguido `...` de, incluído em parênteses; por exemplo, `(controls,...)` .

### <a name="examples"></a>Exemplos

Uma declaração de operação pode ser tão simples como a seguinte, que define a operação primitiva pauli X:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Note-se que o ponto adísquio da operação Pauli X é definido com a diretiva `self` porque, por definição, `X` é o seu próprio inverso.

No exemplo `PrepareEntangledPair` anterior, o código é equivalente ao seguinte código que contém declarações explícitas de especialização: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
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

#### <a name="user-defined-specialization-implementation"></a>Implementação de especialização definida pelo utilizador

Se o compilador não conseguir gerar automaticamente a implementação para uma determinada especialização, ou se uma implementação mais eficiente puder ser dada, então pode definir manualmente a implementação.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
No exemplo anterior, `adjoint invert;` indica que a especialização adjacente deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjacente controlada deve ser gerada invertendo a implementação dada da especialização controlada.

Se uma ou mais especializações para além do corpo predefinido precisar de ser explicitamente declarada, então a implementação do corpo predefinido também deve ser incluída numa declaração de especialização adequada:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>Circunstâncias para a definição válida de especializações

#### <a name="operation-declarations-with-adjointcontrolled"></a>Declarações de operação com adjacentes/controladas

É legal especificar uma operação sem versões adjacentes ou controladas. Por exemplo, as operações de medição não têm, por não serem invertíveis ou controláveis.

Uma operação apoia os `Adjoint` e `Controlled` functors se a sua declaração contiver uma declaração implícita ou explícita das respetivas especializações.

Uma especialização explicitamente declarada adjacente/controlada implica a existência de uma especialização adjacente/controlada. 

Para uma operação cujo corpo contenha ciclos de repetição até ao sucesso, desemote declarações, medições, declarações de devolução ou chamadas para outras operações que não suportem o `Adjoint` functor, gerando automaticamente uma especialização adjacente seguindo a `invert` diretiva ou `auto` diretiva não é possível.

Para uma operação cujo corpo contenha chamadas para outras operações que não suportem o `Controlled` functor, não é possível gerar automaticamente uma especialização controlada seguindo a `distribute` diretiva ou `auto` diretiva.

#### <a name="controlled-adjoint"></a>Controlado adjacente

A versão adjacente controlada de uma operação especifica como implementar uma versão com controlo quântico do adjacente da operação.
É legal especificar uma operação sem versão adjacente controlada; por exemplo, as operações de medição não têm versão adjacente controlada porque não são controláveis nem invertíveis.

Uma especialização adjacente controlada para uma operação tem de existir se e somente se existir uma especialização adjacente e controlada. Nesse caso, é deduzida a existência da especialização adjacente controlada. Se nenhuma implementação for explicitamente definida, o compile gera uma especialização adequada.

Para uma operação cujo corpo contenha chamadas para outras operações que não tenham uma versão adjacente controlada, não é possível gerar automaticamente uma especialização adjacente na sequência do `invert` `distribute` , ou `auto` diretiva.


### <a name="type-compatibility"></a>Compatibilidade tipo

Utilize uma operação com funtores adicionais suportados em qualquer lugar que utilize uma operação com menos funtores, mas a mesma assinatura. Por exemplo, utilize uma operação do tipo `(Qubit => Unit is Adj)` em qualquer lugar que utilize uma operação do tipo `(Qubit => Unit)` .

Q# é *covariante* no que diz respeito aos tipos de retorno callable: uma chamada que devolve um tipo `'A` é compatível com uma chamada com o mesmo tipo de entrada e um tipo de resultado que é compatível com `'A` .

Q# é *contravariante* no que diz respeito aos tipos de entrada: uma chamada que toma um tipo `'A` como entrada é compatível com uma chamada com o mesmo tipo de resultado e um tipo de entrada compatível com `'A` .

Isto é, dadas as seguintes definições,

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

É possível

- Invocar a `ConjugateInvertWith` função com um `inner` argumento de um ou `Invert` `ApplyUnitary` .
- Invoque a `ConjugateUnitaryWith` função com um `inner` argumento `ApplyUnitary` de, mas não `Invert` .
- Devolva um valor de tipo `(Qubit[] => Unit is Adj + Ctl)` a partir de `ConjugateInvertWith` .

> [!IMPORTANT]
> Q# 0.3 introduziu uma diferença significativa no comportamento dos tipos definidos pelo utilizador.

Os tipos definidos pelo utilizador são tratados como uma versão embrulhada do tipo subjacente, em vez de como um subtipo.
Isto significa que um valor de um tipo definido pelo utilizador não é utilizável onde se espera que seja um valor do tipo subjacente.


## <a name="defining-new-functions"></a>Definição de Novas Funções

As funções são puramente determinísticas, rotinas clássicas Q# em, que são distintas das operações na qual não são permitidas a ter quaisquer efeitos além do cálculo de um valor de saída.
Em especial, as funções não podem convocar operações; agir, alocar ou pedir qubits emprestados; amostra de números aleatórios; ou de outra forma dependem do estado para além do valor de entrada para uma função.
Como consequência, Q# as funções são *puras,* na medida em que mapeiam sempre os mesmos valores de entrada para os mesmos valores de saída.
Este comportamento permite ao Q# compilador reencomendar com segurança como e quando chamar funções ao gerar especializações de operação.

Cada Q# ficheiro de origem pode definir qualquer número de funções.
Os nomes das funções devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento ou os nomes do tipo.

A definição de uma função funciona da mesma forma para definir uma operação, exceto que não podem ser definidas especializações adjacentes ou controladas para uma função.
Por exemplo:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

ou 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>Lógica clássica em funções == bom

Sempre que é possível fazê-lo, é útil escrever a lógica clássica em termos de funções em vez de operações para que as operações possam usá-la mais facilmente. Por exemplo, se tivesse escrito a declaração anterior `Square` como *uma operação* , então o compilador não teria sido capaz de garantir que chamá-lo com a mesma entrada produziria consistentemente as mesmas saídas.

Para sublinhar a diferença entre funções e operações, considere o problema da amostragem clássica de um número aleatório de dentro de uma Q# operação:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Cada vez que `U` se chama, tem uma ação `target` diferente.
Em particular, o compilador não pode garantir que, se adicionar uma `adjoint auto` declaração de `U` especialização, age como identidade `U(target); Adjoint U(target);` (isto é, como um não-op).
Isto viola a definição do adjacente definido em [Vetores e Matrizes,](xref:microsoft.quantum.concepts.vectors)de modo que permitir que o compilador gere automaticamente uma especialização adjacente numa operação em que você chama a operação <xref:Microsoft.Quantum.Math.RandomReal> quebraria as garantias fornecidas pelo compilador; é uma operação para a <xref:Microsoft.Quantum.Math.RandomReal> qual não existe nenhuma versão adjacente ou controlada.

Por outro lado, permitir chamadas de funções como `Square` é seguro, e assegura ao compilador que só precisa de preservar a entrada `Square` para manter a sua saída estável.
Assim, isolar o máximo de lógica clássica possível em funções torna fácil a reutilização dessa lógica noutras funções e operações.


## <a name="generic-type-parameterized-callables"></a>Caláveis genéricos (tipo-parametrizados)

Muitas funções e operações que você pode desejar definir não dependem fortemente dos tipos de suas entradas, mas apenas implicitamente usar os seus tipos através de qualquer outra função ou funcionamento.
Por exemplo, considere o conceito de *mapa* comum a muitas línguas funcionais; dada uma função $f(x)$ e uma coleção de valores $ \{ x_1, x_2, \dots, x_n \} $, o mapa devolve uma nova coleção $ \{ f(x_1), f(x_2), \dots, f(x_n) \} $.
Para implementar isto Q# em , aproveite o facto de que as funções são de primeira classe.
Aqui está um exemplo rápido de `Map` , usando `T` como espaço reservado enquanto você descobre que tipos você precisa.

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que esta função parece muito igual independentemente dos tipos reais que substitua.
Um mapa de inteiros a Paulis, por exemplo, parece muito parecido com um mapa de números flutuantes a cordas:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Em princípio, pode escrever uma versão `Map` de todos os tipos que encontrar, mas isto introduz várias dificuldades.
Por exemplo, se encontrar um `Map` bug, deve certificar-se de que a correção é aplicada uniformemente em todas as versões de `Map` .
Além disso, se você constrói um novo tuple ou UDT, então você deve agora também construir um novo `Map` para acompanhar o novo tipo.
Embora isto seja tratável para um pequeno número de tais funções, à medida que recolhe cada vez mais funções da mesma forma `Map` que, o custo de introdução de novos tipos torna-se irracionalmente grande em ordem bastante curta.

No entanto, grande parte desta dificuldade resulta do facto de não ter dado ao compilador a informação de que necessita para reconhecer como as diferentes versões `Map` estão relacionadas.
Efetivamente, pretende-se que o compilador trate `Map` como uma espécie de função matemática, desde Q# *tipos* a Q# funções.

Q# formaliza esta noção permitindo que funções e operações tenham *parâmetros de tipo,* bem como os seus parâmetros comuns de tuple.
Nos exemplos anteriores, pretende-se pensar em ter parâmetros de `Map` tipo no primeiro caso e no segundo `Int, Pauli` `Double, String` caso.
Na maior parte das vezes, utilize estes parâmetros de tipo como se fossem tipos comuns. Utilize valores de parâmetros de tipo para fazer matrizes e tuples, funções de chamada e operações, e atribuir a variáveis comuns ou mutáveis.

> [!NOTE]
> O caso mais extremo de dependência indireta é o dos qubits, onde um Q# programa não pode depender diretamente da estrutura do `Qubit` tipo, mas **deve** passar esses tipos para outras operações e funções.

Voltando ao exemplo anterior, então, você vê que `Map` precisa ter parâmetros de tipo, um para representar a entrada `fn` e outro para representar a saída de `fn` .
Em Q# , isto é escrito adicionando suportes de ângulo (isto `<>` é, não travões $\braket {} $!) após o nome de uma função ou operação na sua declaração, e enumerando cada parâmetro do tipo.
O nome de cada parâmetro do tipo deve começar com um `'` carrapato, indicando que se trata de um parâmetro do tipo e não de um tipo comum (também conhecido como tipo *de betão).*
Assim, `Map` está escrito:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que a definição de `Map<'Input, 'Output>` parece extremamente semelhante às versões previoius.
A única diferença é que informou explicitamente o compilador que `Map` não depende diretamente do que e do que `'Input` `'Output` são, mas funciona para qualquer dois tipos, utilizando-os indiretamente através `fn` de .
Uma vez definido `Map<'Input, 'Output>` desta forma, pode chamá-lo como se fosse uma função comum:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Escrever funções genéricas e operações é um lugar onde "tuple-in tuple-out" é uma forma muito útil de pensar sobre Q# funções e operações.
> Uma vez que cada função requer exatamente uma entrada e devolve exatamente uma saída, uma entrada de tipo `'T -> 'U` corresponde a *qualquer* Q# função.
> Da mesma forma, pode passar qualquer operação a uma entrada do tipo `'T => 'U` .

Como segundo exemplo, considere o desafio de escrever uma função que devolve a composição de duas outras funções:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Aqui, você deve especificar exatamente o que `A` `B` , e `C` estão, portanto, severamente limitando a utilidade da nossa nova `Compose` função.
Afinal, `Compose` só depende `A` de `B` , e `C` *via* `innerFn` e `outerFn` .
Como alternativa, então, pode adicionar parâmetros de tipo `Compose` a que indicam que funciona para *qualquer* , e , desde que `A` estes `B` `C` parâmetros correspondam aos esperados por `innerFn` `outerFn` e:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

As Q# bibliotecas-padrão fornecem uma gama de operações e funções por tipo-parametrizadas para facilitar a expressão do fluxo de controlo de ordem superior.
Estes são discutidos mais adiante no [ Q# guia padrão](xref:microsoft.quantum.libraries.standard.intro)da biblioteca.


## <a name="callables-as-first-class-values"></a>Calíveis como valores First-Class

Uma técnica crítica para o raciocínio sobre o fluxo de controlo e a lógica clássica utilizando funções em vez de operações é utilizar que as operações e as funções Q# são de primeira *classe* .
Ou seja, são valores cada um na língua por direito próprio.
Por exemplo, o seguinte é um código perfeitamente Q# válido, se um pouco indireto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

O valor da variável `ourH` no corte anterior é então a operação , de modo a que possa chamar esse valor como qualquer outra <xref:Microsoft.Quantum.Intrinsic.H> operação.
Com esta capacidade, pode escrever operações que tomem operações como parte da sua entrada, formando conceitos de fluxo de controlo de ordem superior.
Por exemplo, pode imaginar querer "quadrar" uma operação aplicando-a duas vezes ao mesmo qubit alvo.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Operações de regresso de uma função

É importante enfatizar que também pode devolver operações como parte das saídas, de modo a que possa isolar alguns tipos de lógica condicional clássica como uma função clássica, que devolve uma descrição de um programa quântico sob a forma de uma operação.
Como exemplo simples, considere o exemplo de teletransporte, no qual o partido que recebe uma mensagem clássica de duas partes precisa de usar a mensagem para descodificar o seu qubit no estado teletransportado adequado.
Você poderia escrever isto em termos de uma função que pega nessas duas partes clássicas e devolve a operação de descodição adequada.

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

Esta nova função é de facto uma função, na qual se lhe chamarmos com os mesmos valores `hereBit` de `thereBit` e, você sempre recebe de volta a mesma operação.
Assim, o descodificador pode executar com segurança operações internas sem ter de raciocinar sobre como a lógica de descodificante interage com as definições das diferentes especializações de operação.
Ou seja, a lógica clássica dentro de uma função é isolada, garantindo ao compilador que a chamada de função pode ser reordenada com impunidade enquanto a entrada for preservada.


## <a name="partial-application"></a>Aplicação Parcial

Pode fazer significativamente mais com funções que devolvem as operações utilizando *uma aplicação parcial,* na qual fornece uma ou mais partes da entrada para uma função ou funcionamento sem realmente chamá-la. No exemplo `ApplyTwice` anterior, pode indicar que não pretende especificar, de imediato, qual o qubit da operação de entrada:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Neste caso, a variável local `twiceOp` detém a operação parcialmente `ApplyTwice(op, _)` aplicada, onde `_` indica partes da entrada que ainda não foram especificadas.
Quando ligar `twiceOp` na linha seguinte, passa como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.
Assim, o corte anterior é efetivamente idêntico a ter chamado `ApplyTwice(op, target)` diretamente, salvo para que tenha introduzido uma nova variável local para que possa atrasar a chamada enquanto fornece algumas partes da entrada.

Uma vez que uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, você pode aplicar parcialmente as operações mesmo a partir de funções.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Em princípio, a lógica clássica dentro de si `SquareOperation` poderia ter sido muito mais envolvida, mas ainda está isolada do resto de uma operação pelas garantias que o compilador pode oferecer sobre funções. A Q# biblioteca padrão usa esta abordagem ao longo de todo para expressar o fluxo de controlo clássico de uma forma que os programas quânticos podem facilmente usar.


## <a name="recursion"></a>Recursão

Q# as calções podem ser direta ou indiretamente recursivas.
Ou seja, uma operação ou função pode chamar-se a si mesma, ou pode chamar outra chamada que, direta ou indiretamente, chama a operação callable.

No entanto, existem dois comentários importantes sobre a utilização da recursão:

- A utilização de recursões nas operações é suscetível de interferir com determinadas otimizações.
  Esta interferência pode ter um impacto substancial no tempo de execução do algoritmo.
- Ao correr num dispositivo quântico real, o espaço da pilha pode ser limitado, e assim a recursão profunda pode levar a um erro de tempo de execução.
  Em particular, o compilador e o Q# tempo de execução não identificam e otimizam a recursão da cauda.

## <a name="next-steps"></a>Passos seguintes

Saiba mais sobre [variáveis](xref:microsoft.quantum.guide.variables) em Q# .