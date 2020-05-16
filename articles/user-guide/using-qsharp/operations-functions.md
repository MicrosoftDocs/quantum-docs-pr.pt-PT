---
title: 'Operações e funções em Q #'
description: Como definir e chamar operações e funções, bem como as especializações de operação controlada e adjoint.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431075"
---
# <a name="operations-and-functions-in-q"></a>Operações e Funções em Q #

## <a name="defining-new-operations"></a>Definição de Novas Operações

As operações são o núcleo do Q#.
Uma vez declarados, podem ser chamados de aplicações clássicas .NET, por exemplo, utilizando um simulador, ou por outras operações dentro do Q#.
Cada operação definida em Q# pode então chamar qualquer número de outras operações, incluindo as operações intrínsecas incorporadas definidas pela língua. A forma particular como estas operações intrínsecas são definidas depende da máquina-alvo.
Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.

Cada ficheiro de origem Q# pode definir qualquer número de operações.
Os nomes de funcionamento devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de tipo ou função.

Uma declaração de operação consiste na palavra-chave, `operation` seguida do símbolo que é o nome da operação, de uma túnica identificada dactilografada que define os argumentos da operação, de um `:` cólon, de uma anotação tipo que descreve o tipo de resultado da operação, opcionalmente uma anotação com as características de funcionamento, uma cinta `{` aberta, o corpo da declaração de funcionamento e um aparelho de fecho `}` final.

Cada operação tem uma entrada, produz uma saída e especifica a implementação para uma ou mais especializações de operação.
As possíveis especializações, e como defini-las/chamá-las, são detalhadas mais abaixo.
Para já, considere a seguinte operação, que define apenas uma especialização corporal padrão e toma um único qubit como entrada, e depois chama a operação incorporada <xref:microsoft.quantum.intrinsic.x> nessa entrada:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A palavra-chave começa a definição de `operation` operação, e é seguida pelo nome; aqui, `BitFlip` .
Em seguida, o tipo de entrada é definido `Qubit` como, juntamente com um nome `target` para se referir à entrada dentro da nova operação.
Da mesma forma, os `Unit` definidos definem que a saída da operação está vazia.
Isto é usado da mesma forma `void` em C# e outras línguas imperativas, e é equivalente a `unit` F# e outras línguas funcionais.

As operações também podem devolver tipos mais interessantes do que `Unit` .
Por exemplo, a <xref:microsoft.quantum.intrinsic.m> operação devolve uma saída de `Result` tipo, representando ter efetuado uma medição. Podemos passar a saída de uma operação para outra operação, ou podemos usá-la com a `let` palavra-chave para definir uma nova variável.

Isto permite representar a computação clássica que interage com operações quânticas a um nível baixo, como na [codificação superdensa:](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)

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
> Cada operação em Q# leva exatamente uma entrada e devolve exatamente uma saída.
> Várias inputs e saídas são então representadas usando *tuples,* que recolhem múltiplos valores juntos num único valor.
> Informalmente, dizemos que Q# é uma linguagem "tuple-in tuple-out".
> Seguindo este conceito, `()` deve então ser lido como o tuple "vazio", que tem o tipo `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Operações controladas e adjoint

Se uma operação implementar uma transformação unitária, como é o caso de muitas operações em Q#, então é possível definir como a operação funciona quando *adjoint ou* *controlada*. Uma especialização *conjunta* de uma operação especifica como funciona o "inverso" da operação, enquanto uma especialização *controlada* especifica como uma operação funciona quando a sua aplicação está condicionada no estado de um determinado registo quântico.

As articulações de operações quânticas são cruciais para muitos aspetos da computação quântica. Mais abaixo, na secção [Conjugações,](#conjugations) encontrará uma dessas situações discutida seletivamente ao lado de uma técnica de programação Q# útil.

A versão controlada de uma operação é uma nova operação que aplica eficazmente o funcionamento da base apenas se todos os qubits de controlo estiverem num estado determinado.
Se os qubits de controlo estiverem em sobreposição, então o funcionamento da base é aplicado de forma coerente à parte adequada da superposição.
Assim, as operações controladas são frequentemente usadas para gerar emaranhado.

Naturalmente, também poderia existir uma especialização *adjoint controlada,* especificando a aplicação controlada do adjoint de uma operação.

> [!NOTE]
> Se $U$ é a transformação unitária implementada por uma `U` operação, então `Adjoint U` representa a transformação unitária $U^\dagger$, que é o complexo conjugado transpor.
> Sucessivamente aplicando uma operação e, em seguida, o seu adjoint a um estado deixa o Estado inalterado, como ilustrado pelo facto de $UU^\dagger = U^\dagger U = \id$, a matriz de identidade.
> A representação unitária de uma operação controlada é um pouco mais matizada, mas pode encontrar mais detalhes nos [conceitos de computação quântica: múltiplos qubits](xref:microsoft.quantum.concepts.multiple-qubits).

A secção seguinte descreve como chamar estas várias especializações no seu código Q#.
Abaixo, detalhamos como definir operações para apoiá-las.

### <a name="calling-operation-specializations"></a>Call operation especializações

Um *functor* em Q# é uma fábrica que define uma nova operação a partir de outra operação.
Os dois functores padrão em Q# são `Adjoint` e `Controlled` .

Os functores têm acesso à implementação da operação base na definição da implementação da nova operação.
Assim, os functores podem desempenhar funções mais complexas do que as funções tradicionais de alto nível. Os functores não têm representação no sistema do tipo Q#. Por conseguinte, não é atualmente possível ligá-los a uma variável ou aprová-los como argumentos. 

Um functor é utilizado aplicando-o a uma operação, devolvendo uma nova operação.
Por exemplo, a operação que resulta da aplicação do `Adjoint` functor à `Y` operação é escrita como `Adjoint Y` .
A nova operação pode então ser invocada como qualquer outra operação.
Para uma operação de apoio à aplicação dos `Adjoint` functores e/ou `Controlled` functores, o seu tipo de devolução precisa necessariamente de ser `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`functor

Assim, `Adjoint Y(q1)` aplica-se o functor Adjoint à `Y` operação para gerar uma nova operação, e aplica-se essa nova operação a `q1` .
A nova operação tem a mesma assinatura e tipo que o funcionamento da base `Y` .
Em particular, a nova operação também `Adjoint` permite, e permitirá `Controlled` se e apenas se a operação base o fez.
O functor Adjoint é o seu próprio inverso; isto é, `Adjoint Adjoint Op` é sempre o mesmo `Op` que.

#### <a name="controlled-functor"></a>`Controlled`functor

Da mesma forma, `Controlled X(controls, target)` aplica-se o functor controlado à `X` operação para gerar uma nova operação, e aplica essa nova operação para e `controls` `target` .

> [!NOTE]
> Em Q#, as versões controladas tomam sempre uma série de qubits de controlo, e o estado especificado é sempre para todos os qubits de controlo estarem no estado computacional , `PauliZ` `One` $\ket {1} $.
> O controlo baseado noutros Estados pode ser alcançado aplicando a operação unitária adequada aos qubits de controlo antes da operação controlada e aplicando os inversos da operação unitária após a operação controlada.
> Por exemplo, aplicar uma operação a um qubit de controlo antes e depois de uma operação controlada fará com que `X` a operação controle o `Zero` estado ($\ket {0} $) para esse qubit; aplicação de uma `H` operação antes e depois controlará o `PauliX` `One` estado, ou seja, -1 eigenvalue de Pauli X, $\ket {-} \mathrel{:=} {0} (\ket - \ket {1} ) / \sqrt {2} $ em vez do `PauliZ` `One` estado.

Dada a expressão de operação, pode ser formada uma nova expressão de operação utilizando o `Controlled` functor.
A assinatura da nova operação baseia-se na assinatura da operação original.
O tipo de resultado é o mesmo, mas o tipo de entrada é um dois tuple com uma matriz qubit que detém o qubit de controlo como primeiro elemento e os argumentos da operação original como segundo elemento.
A nova operação apoia `Controlled` , e apoiará `Adjoint` se e apenas se a operação original o fizer.

Se a operação original teve apenas um único argumento, então a equivalência de tuple singleton entrará em jogo aqui.
Por exemplo, `Controlled X` é a versão controlada da `X` operação. 
`X`tem `(Qubit => Unit is Adj + Ctl)` tipo, assim `Controlled X` como tem `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` tipo; por causa da equivalência de tuple singleton, este é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Se a operação base tomou vários argumentos, lembre-se de encerrar os argumentos correspondentes da versão controlada da operação em parênteses para convertê-los em um tuple.
Por exemplo, `Controlled Rz` é a versão controlada da `Rz` operação. 
`Rz`tem `((Double, Qubit) => Unit is Adj + Ctl)` tipo, assim `Controlled Rz` tem tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Assim, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (note os parênteses ao `0.1, target` redor).

Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)` . Se um alvo deve ser controlado por 2 qubits de controlo (CCNOT), podemos utilizar `Controlled X([control1, control2], target)` a declaração.

#### `Controlled Adjoint` 

Os `Controlled` `Adjoint` functores e functores viajam, pelo que não há diferença entre candidatar `Controlled Adjoint Op` ou `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definição de implementações controladas e adjoint

Na primeira declaração de operação, os exemplos acima referidos, as operações `BitFlip` foram `DecodeSuperdense` definidas com assinaturas `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` e, respectivamente.
Como `DecodeSuperdense` inclui medições, não se trata de uma operação unitária e, por conseguinte, não poderia existir especializações adjoint não controladas (recorde-se a exigência conexa de que tal operação devolução `Unit` ).
No entanto, como `BitFlip` simplesmente executa a operação unitária, <xref:microsoft.quantum.intrinsic.x> poderíamos tê-la definido com ambas as especializações.

Aqui, detalhamos como incluir a existência de especializações nas suas declarações de operação Q#, dando-lhes assim a capacidade de ligar em conjunto com os `Adjoint` e/ou `Controlled` functors.
Mais [abaixo,](#circumstances-for-validly-defining-specializations)descrevemos algumas das situações em que é válida ou não válida para declarar determinadas especializações.

As características de funcionamento definem que tipos de functores podem ser aplicados à operação declarada e que efeito têm. A existência destas especializações pode ser declarada como parte da assinatura da operação, especificamente através de uma anotação com as características de funcionamento: `is Adj` ou, `is Ctl` ou `is Adj + Ctl` .
A implementação real de cada especialização pode ser *definida implicitamente* ou *explicitamente.*

### <a name="implicitly-specifying-implementations"></a>Especificando implicitamente as implementações

Neste caso, o organismo da declaração de operação consiste exclusivamente na aplicação por defeito. Por exemplo:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
Aqui, a implementação correspondente para cada uma dessas especialização declarada sem fim é automaticamente gerada pelo compilador, a ser realizada se os `Adjoint` `Controlled` functores ou functores forem utilizados.

Assim, uma chamada resultaria `Adjoint PrepareEntangledPair` na implementação do compilador da adjoint de `CNOT` e, em seguida, do adjoint de `H` .
Estas operações individuais são simultaneamente auto-adjoint, pelo que a operação resultante `Adjoint PrepareEntangledPair` consistiria simplesmente na aplicação `CNOT(here, there)` `H(here)` e, em seguida, em .
Assim, podemos usá-lo para escrever o `DecodeSuperdense` exemplo acima de forma mais compacta, usando a adjoint de transformar o estado emaranhado de volta em um par de `PrepareEntangledPair` qubits sem emaranhado:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

A anotação com as características de funcionamento na declaração é útil para garantir que o compilador gera automaticamente outras especializações com base na implementação padrão. 

Há uma série de limitações importantes a ter em conta na conceção de operações de utilização com functors.
Mais criticamente, as especializações para uma operação que utilize o valor de saída de qualquer outra operação *não podem* ser geradas automaticamente pelo compilador, uma vez que é ambígua como reordenar as declarações numa operação deste tipo para obter o mesmo efeito.

Por conseguinte, é muitas vezes útil especificar explicitamente as várias implementações.

### <a name="explicitly-specifying-implementations"></a>Especificação explícita das implementações

No caso de a implementação não poder ser gerada pelo compilador, pode ser explicitamente especificada. Tais declarações explícitas de especialização podem consistir numa diretiva de *geração* adequada ou numa aplicação definida pelo utilizador.
Aqui fornecemos toda a gama de possibilidades, com exemplos a seguir abaixo.


#### <a name="explicit-specialization-declarations"></a>Declarações explícitas de especialização

Q# as operações podem conter as seguintes declarações explícitas de especialização:

- A `body` especialização especifica a implementação da operação sem functores aplicados.
- A `adjoint` especialização especifica a implementação da operação com o `Adjoint` functor aplicado.
- A `controlled` especialização especifica a implementação da operação com o `Controlled` functor aplicado.
- A `controlled adjoint` especialização especifica a implementação da operação com os `Adjoint` functores e os `Controlled` functors aplicados.
  Esta especialização também pode ser `adjoint controlled` nomeada, uma vez que os dois functors viajam.


Uma especialização de operação consiste na etiqueta de especialização (por `body` exemplo, `adjoint` ou, etc.) seguida de uma das:

- Uma declaração explícita, como descrito abaixo.
- Uma *diretiva* que diz ao compilador *como* gerar a especialização, uma das:
  - `intrinsic`, o que indica que a especialização é fornecida pela máquina-alvo.
  - `distribute`, que pode ser utilizado com `controlled` e `controlled adjoint` especializações.
    Quando utilizado `controlled` com, indica que o compilador deve calcular a especialização aplicando-se `Controlled` a todas as operações na `body` .
    Quando utilizado `controlled adjoint` com, indica que o compilador deve calcular a especialização aplicando-se `Controlled` a todas as operações na `adjoint` especialização.
  - `invert`, o que indica que o compilador deve calcular a `adjoint` especialização invertendo a `body` ordem de operações e aplicando o adjoint a cada um.
    Quando utilizado `adjoint controlled` com, isto indica que o compilador deve calcular a especialização invertendo a `controlled` especialização.
  - `self`, para indicar que a especialização adjoint é a mesma que a `body` especialização.
    Isto é legal para as `adjoint` `adjoint controlled` e especializações.
    Pois, `adjoint controlled` `self` implica que a `adjoint controlled` especialização é a mesma que a `controlled` especialização.
  - `auto`, para indicar que o compilador deve selecionar uma diretiva adequada a aplicar.
    `auto`não pode ser utilizado para a `body` especialização.

As diretivas e `auto` todos exigem um fecho do ponto-de-vírgula. `;`
A `auto` diretiva resolve-se com a seguinte diretiva de geração se for fornecida uma declaração `body` explícita:

- A `adjoint` especialização é gerada de acordo com a `invert` diretiva.
- A `controlled` especialização é gerada de acordo com a `distribute` diretiva.
- A `adjoint controlled` especialização é gerada de acordo com a diretiva `invert` se for dada uma declaração explícita, mas não uma para , e de outra `controlled` `adjoint` `distribute` forma.

> [!TIP]   
> Se uma operação for auto-adjoint, especifique explicitamente a adjoint ou a especialização adjoint controlada através da diretiva de geração, a fim de `self` permitir que o compilador utilize essa informação para fins de otimização.

Uma declaração de especialização contendo uma implementação definida pelo utilizador consiste num argumento de tuple seguido de um bloco de declaração com o código Q# que implementa a especialização.
Na lista de argumentos, `...` é utilizado para representar os argumentos declarados para a operação como um todo.
Pois e , a lista de argumentos deve ser sempre - para e , a lista de `body` argumentos deve ser um símbolo que `adjoint` `(...)` `controlled` `adjoint controlled` represente o conjunto de qubits de controlo, seguidos por `...` , fechados em parênteses; por exemplo, `(controls,...)` .

### <a name="examples"></a>Exemplos

Uma declaração de operação pode ser tão simples como a seguinte, que define a operação primitiva Pauli X:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Note-se que o adjoint da operação Pauli X é definido com a diretiva `self` porque, por `X` definição, é o seu próprio inverso.

O código `PrepareEntangledPair` acima, por exemplo, equivale ao código abaixo contendo declarações explícitas de especialização: 

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

#### <a name="user-defined-specialization-implementation"></a>Implementação da especialização definida pelo utilizador

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

Se uma ou mais especializações para além do corpo padrão precisarde matem explicitamente, então a implementação do organismo predefinido deve ser embrulhada numa declaração de especialização adequada:

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

### <a name="circumstances-for-validly-defining-specializations"></a>Circunstâncias para definir validamente especializações

#### <a name="operation-declarations-with-adjointcontrolled"></a>Declarações de operação com adjoint/controlada

É legal especificar uma operação sem versões adjoint ou controlada. Por exemplo, as operações de medição não têm nenhuma, porque não são invertáveis ou controláveis.

Uma operação apoia os `Adjoint` e/ou `Controlled` functores se a sua declaração contiver uma declaração implícita ou explícita das respetivas especializações.

Uma especialização adjoint/controlada explicitamente declarada implica a existência de uma especialização adjoint/controlada. 

Para uma operação cujo corpo contenha ciclos de repetição até ao sucesso, definir declarações, medições, declarações de devolução ou chamadas para outras operações que não suportem o `Adjoint` functor, gerando automaticamente uma especialização adjoint seguindo a ou diretiva `invert` `auto` não é possível.

Para uma operação cujo corpo contenha chamadas para outras operações que não suportem o `Controlled` functor, não é possível gerar automaticamente uma especialização controlada na sequência da `distribute` ou `auto` diretiva.

#### <a name="controlled-adjoint"></a>Adjoint controlado

A versão adjoint controlada de uma operação especifica como é implementada uma versão quântica da adjoint da operação.
É legal especificar uma operação sem versão adjoint controlada; por exemplo, as operações de medição não têm versão adjoint controlada porque não são controláveis nem invertíveis.

Uma especialização adjoint controlada para uma operação precisa de existir se e apenas se existir uma especialização adjoint e controlada. Nesse caso, a existência da especialização adjoint controlada é inferida e uma especialização adequada é gerada pelo compilador se não tiver sido definida explicitamente nenhuma implementação. 

Para uma operação cujo corpo contenha chamadas para outras operações que não tenham uma versão adjoint controlada, não é possível gerar automaticamente uma especialização adjoint na sequência da `invert` diretiva `distribute` ou `auto` diretiva.


### <a name="type-compatibility"></a>Compatibilidade tipo

Uma operação com functores adicionais suportados pode ser usada em qualquer lugar de uma operação com menos functores, mas a mesma assinatura é esperada.
Por exemplo, pode ser utilizada uma operação de tipo `(Qubit => Unit is Adj)` em qualquer lugar que se espere uma operação de `(Qubit => Unit)` tipo.

Q# é *covariante* em relação aos tipos de retorno caltáveis: um callable que devolve um tipo é compatível com um callable com o mesmo tipo de entrada e um tipo de `'A` resultado compatível `'A` com.

Q# é *contravariante* em relação aos tipos de entrada: um callable que toma um tipo `'A` como entrada é compatível com um callable com o mesmo tipo de resultado e um tipo de entrada compatível com `'A` .

Ou seja, dadas as seguintes definições:

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

os seguintes são verdadeiros:

- A função `ConjugateInvertWith` pode ser invocada com um `inner` argumento de qualquer um ou `Invert` `ApplyUnitary` .
- A função `ConjugateUnitaryWith` pode ser invocada com um `inner` argumento `ApplyUnitary` de, mas `Invert` não.
- Um valor de tipo `(Qubit[] => Unit is Adj + Ctl)` pode ser devolvido a partir de `ConjugateInvertWith` .

> [!IMPORTANT]
> Q# 0.3 introduziu uma diferença significativa no comportamento dos tipos definidos pelo utilizador.

Os tipos definidos pelo utilizador são tratados como uma versão embrulhada do tipo subjacente, em vez de como um subtipo.
Isto significa que um valor de um tipo definido pelo utilizador não é utilizável quando se espera um valor do tipo subjacente.


### <a name="conjugations"></a>Conjugações

Em contraste com as partes clássicas, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejados no restante cálculo se os qubits ainda estiverem emaranhados. Isto pode ser evitado por "desfazer" corretamente as computações realizadas antes de libertar a memória. Um padrão comum na computação quântica é, portanto, o seguinte: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

A partir do nosso lançamento 0.9, apoiamos uma declaração de conjugação que implementa a transformação acima. Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Tal declaração de conjugação torna-se obviamente muito mais útil se a transformação exterior e interior não estiver prontamente disponível como operações, mas em vez disso são mais convenientes para descrever por um bloco composto por várias declarações. 

A transformação inversa para as declarações definidas no bloco interior é automaticamente gerada pelo compilador e executada após a conclusão do bloco de aplicação.
Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente a adjoint do cálculo no bloco interior. 


## <a name="defining-new-functions"></a>Definição de novas funções

As funções são puramente deterministas, rotinas clássicas em Q#, que são distintas das operações na medida em que não estão autorizadas a ter quaisquer efeitos além do cálculo de um valor de saída.
Em especial, as funções não podem chamar operações; Agir sobre, atribuir ou emprestar qubits; números aleatórios de amostra; ou depender do estado para além do valor de entrada para uma função.
Como consequência, as funções Q# são *puras,* na medida em que sempre mapeiam os mesmos valores de entrada para os mesmos valores de saída.
Isto permite ao compilador Q# reordenar com segurança como e quando as funções são chamadas ao gerar especializações de operação.

Cada ficheiro de origem Q# pode definir qualquer número de funções.
Os nomes de funções devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de funcionamento ou tipo.

A definição de uma função funciona da mesma forma para definir uma operação, exceto que nenhuma especialização adjoint ou controlada pode ser definida para uma função.
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

Sempre que é possível fazê-lo, é útil escrever a lógica clássica em termos de funções e não de operações, para que possa ser mais facilmente utilizada a partir de dentro das operações.
Por exemplo, se tivéssemos escrito a `Square` declaração acima como *operação,* então o compilador não teria podido garantir que chamá-la com a mesma entrada produziria consistentemente as mesmas saídas.

Para sublinhar a diferença entre funções e operações, considere o problema da amostragem clássica de um número aleatório de dentro de uma operação Q#:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Cada vez que `U` for chamado, terá uma ação `target` diferente.
Em particular, o compilador não pode garantir que, se adicionássemos uma declaração de `adjoint auto` especialização, `U` `U(target); Adjoint U(target);` então atua como identidade (isto é, como uma não-operação).
Isto viola a definição da adjoint que vimos em [Vetores e Matrizes](xref:microsoft.quantum.concepts.vectors), de tal forma que permitir gerar automaticamente uma especialização adjoint numa operação em que chamámos operação <xref:microsoft.quantum.math.randomreal> quebraria as garantias fornecidas pelo compilador; é uma operação para a qual não existe nenhuma <xref:microsoft.quantum.math.randomreal> versão adjoint ou controlada.

Por outro lado, permitir chamadas de funções como `Square` é segura, na medida em que o compilador pode ter a certeza de que só precisa de preservar a entrada `Square` para manter a sua produção estável.
Assim, isolar o máximo de lógica clássica possível em funções facilita a reutilização dessa lógica em outras funções e operações.


## <a name="generic-type-parameterized-callables"></a>Callables genéricos (tipo-parametrizados)

Muitas funções e operações que podemos querer definir não dependem muito dos tipos das suas inputs, mas apenas utilizam implicitamente os seus tipos através de outra função ou operação.
Por exemplo, considere o conceito de *mapa* comum a muitas línguas funcionais; dada uma função $f(x)$ e uma coleção de valores $ \{ x_1, x_2, \dots, x_n \} $, mapa devolve uma nova coleção $ \{ f(x_1), f(x_2), \dots, f(x_n) \} $.
Para implementar isto em Q#, podemos tirar partido dessas funções são de primeira classe.
Vamos escrever um exemplo rápido `Map` de, usando ★ como espaço reservado enquanto descobrimos que tipos precisamos.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que esta função parece muito a mesma, independentemente dos tipos reais em que substituímos.
Um mapa de inteiros a Paulis, por exemplo, parece muito parecido com um mapa de números de pontos flutuantes a cordas:

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

Em princípio, poderíamos escrever uma versão de `Map` cada par de tipos que encontramos, mas isso introduz uma série de dificuldades.
Por exemplo, se encontrarmos um `Map` bug, então temos de garantir que a correção é aplicada uniformemente em todas as versões de `Map` .
Além disso, se construirmos um novo tuple ou UDT, então temos agora também de construir um novo `Map` para acompanhar o novo tipo.
Embora isto seja tratável para um pequeno número de tais funções, à medida que recolhemos cada vez mais funções da mesma forma `Map` que, o custo de introdução de novos tipos torna-se irracionalmente grande em ordem bastante curta.

Grande parte desta dificuldade resulta, no entanto, do facto de não termos dado ao compilador a informação de que necessita para reconhecer como as diferentes versões `Map` estão relacionadas.
Efetivamente, queremos que o compilador trate `Map` como uma espécie de função matemática dos *tipos* Q# para as funções Q#.

Esta noção é formalizada permitindo que funções e operações tenham *parâmetros de tipo,* bem como os seus parâmetros normais de tuple.
Nos exemplos acima referidos, queremos pensar `Map` que têm parâmetros de tipo `Int, Pauli` no primeiro caso e no segundo `Double, String` caso.
Na maior parte dos casos, estes parâmetros de tipo podem então ser usados como se fossem tipos comuns: usamos valores de parâmetros de tipo para fazer matrizes e tuples, funções de chamada e operações, e atribuir a variáveis ordinárias ou mutáveis.

> [!NOTE]
> O caso mais extremo de dependência indireta é o dos qubits, onde um programa Q# não pode depender diretamente da estrutura do `Qubit` tipo, mas **deve** passar esses tipos para outras operações e funções.

Voltando ao exemplo acima, podemos ver que precisamos de `Map` ter parâmetros de tipo, um para representar a entrada `fn` e um para representar a saída de `fn` .
Em Q#, isto é escrito adicionando suportes de ângulo (isto `<>` é, não travões $\travão {} $!) após o nome de uma função ou operação na sua declaração, e listando cada parâmetro de tipo.
O nome de cada parâmetro de tipo deve começar com um `'` carrapato, indicando que se trata de um parâmetro tipo e não de um tipo ordinário (também conhecido como tipo *de concreto).*
Pois, `Map` nós assim escrevemos:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que a definição de `Map<'Input, 'Output>` é extremamente semelhante às versões que escrevemos anteriormente.
A única diferença é que informamos explicitamente o compilador que `Map` não depende diretamente do que `'Input` e `'Output` são, mas funciona para qualquer dois tipos, utilizando-os indiretamente através `fn` de .
Uma vez `Map<'Input, 'Output>` definidos desta forma, podemos chamá-lo como se fosse uma função comum:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Escrever funções e operações genéricas é um lugar onde "tuple-in tuple-out" é uma forma muito útil de pensar sobre as funções e operações q#.
> Uma vez que cada função requer exatamente uma entrada e devolve exatamente uma saída, uma entrada de tipo `'T -> 'U` corresponde a *qualquer* função Q# qualquer.
> Da mesma forma, qualquer operação pode ser passada para uma entrada de tipo `'T => 'U` .

Como segundo exemplo, considere o desafio de escrever uma função que retorne a composição de duas outras funções:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Aqui, temos de especificar exatamente o `A` `B` que, e `C` estamos, portanto, a limitar severamente a utilidade da nossa nova `Compose` função.
Afinal, `Compose` só depende `A` de, e `B` `C` *via* `innerFn` e `outerFn` .
Como alternativa, então, podemos adicionar parâmetros de tipo `Compose` que indicam que funciona para *qualquer,* e , desde que `A` estes `B` `C` parâmetros correspondam aos esperados por `innerFn` `outerFn` e:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

As bibliotecas padrão Q# fornecem uma gama dessas operações e funções paramétricas tipo para facilitar o fluxo de controlo de ordem mais fácil de expressar.
Estes são discutidos mais no guia padrão da [biblioteca Q#](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Callables como Valores de Primeira Classe

Uma técnica crítica para o raciocínio sobre o fluxo de controlo e a lógica clássica usando funções em vez de operações é utilizar que as operações e funções em Q# são *de primeira classe*.
Ou seja, são cada valores da língua por direito próprio.
Por exemplo, o seguinte é perfeitamente válido código Q#, se um pouco indireto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

O valor da variável `ourH` no corte acima é então a operação , de modo a que <xref:microsoft.quantum.intrinsic.h> possamos chamar esse valor como qualquer outra operação.
Isto permite-nos escrever operações que tomam as operações como parte da sua entrada, formando conceitos de fluxo de controlo de maior ordem.
Por exemplo, podemos imaginar querer "quadrar" uma operação aplicando-a duas vezes ao mesmo qubit alvo.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Operações de devolução de uma função

Sublinhamos que também podemos devolver as operações como parte das saídas, de modo a que possamos isolar alguns tipos de lógica condicional clássica como função clássica que devolve uma descrição de um programa quântico sob a forma de uma operação.
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

Esta nova função é, de facto, uma função, na forma de a chamarmos com os mesmos valores `hereBit` de `thereBit` e, teremos sempre de volta a mesma operação.
Assim, o descodificador pode ser executado com segurança dentro de operações sem ter de raciocinar sobre como a lógica de descodificação interage com as definições das diferentes especializações de operação.
Ou seja, isolamos a lógica clássica dentro de uma função, garantindo ao compilador que a chamada de função pode ser reordenada impunemente enquanto a entrada for preservada.


## <a name="partial-application"></a>Aplicação parcial

Podemos fazer significativamente mais com funções que devolvem as operações utilizando *aplicações parciais,* nas quais podemos fornecer uma ou mais partes da entrada a uma função ou operação sem realmente chamá-lo. Por exemplo, recordando o `ApplyTwice` exemplo acima, podemos indicar que não queremos especificar, imediatamente, a que qubit a operação de entrada deve aplicar:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Neste caso, a variável local `twiceOp` detém o funcionamento parcialmente `ApplyTwice(op, _)` aplicado, onde partes da entrada que ainda não foram especificadas são indicadas por `_` .
Quando realmente ligamos `twiceOp` para a linha seguinte, passamos como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.
Assim, o corte acima é efetivamente idêntico ao de ter chamado `ApplyTwice(op, target)` diretamente, salvo para isso introduzimos uma nova variável local que nos permite atrasar a chamada, fornecendo algumas partes da entrada.

Uma vez que uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, podemos aplicar parcialmente as operações mesmo a partir de funções.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Em princípio, a lógica clássica no seu interior `SquareOperation` poderia ter sido muito mais envolvida, mas continua isolada do resto de uma operação pelas garantias que o compilador pode oferecer sobre funções.
Esta abordagem será usada em toda a biblioteca padrão Q# para expressar o fluxo de controlo clássico de uma forma que pode ser facilmente usada dentro de programas quânticos.


## <a name="recursion"></a>Recursão

Q# os callables são permitidos ser direta ou indiretamente recursivos.
Ou seja, uma operação ou função pode chamar-se a si mesma, ou pode chamar outra chamada que, direta ou indiretamente, chama a operação de chamada.

No entanto, existem dois comentários importantes sobre a recura:

- A utilização da recursição nas operações é suscetível de interferir com determinadas otimizações.
  Isto pode ter um impacto substancial no tempo de execução do algoritmo.
- Ao executar um dispositivo quântico real, o espaço da pilha pode ser limitado, e assim a recursão profunda pode levar a um erro de tempo de execução.
  Em particular, o compilador Q# e o tempo de execução não identificam e otimizam a recursão da cauda.

## <a name="whats-next"></a>O que se segue?
Saiba mais sobre [Variáveis](xref:microsoft.quantum.guide.variables) em Q#.