---
title: 'Operações e funções em Q #'
description: Como definir e chamar operações e funções, bem como as especializações de operação controladas e adjacentes.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630217"
---
# <a name="operations-and-functions-in-q"></a>Operações e Funções em Q #

## <a name="defining-new-operations"></a>Definição de Novas Operações

As operações são o núcleo de Q#.
Uma vez declarados, podem ser chamados a partir de aplicações clássicas .NET, por exemplo, usando um simulador, ou por outras operações dentro de Q#.
Cada operação definida em Q# pode então chamar qualquer número de outras operações, incluindo as operações intrínsecas incorporadas definidas pelo idioma. A forma particular como estas operações intrínsecas são definidas depende da máquina-alvo.
Quando compilado, cada operação é representada como um tipo de classe .NET que pode ser fornecido às máquinas-alvo.

Cada ficheiro de origem Q# pode definir qualquer número de operações.
Os nomes de operação devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de tipo ou função.

Uma declaração de operação consiste na palavra-chave, `operation` seguida do símbolo que é o nome da operação, um tuple identificador dactilografado que define os argumentos para a operação, um `:` cólon, uma anotação tipo que descreve o tipo de resultado da operação, opcionalmente uma anotação com as características de funcionamento, uma cinta `{` aberta, o corpo da declaração de operação, e uma cinta final de fecho `}` .

Cada operação leva uma entrada, produz uma saída, e especifica a implementação para uma ou mais especializações de operação.
As possíveis especializações, e como defini-las/chamá-las, são detalhadas mais abaixo.
Por enquanto, considere a seguinte operação, que define apenas uma especialização do corpo predefinido e toma um único qubit como sua entrada, em seguida, chama a operação incorporada <xref:microsoft.quantum.intrinsic.x> nessa entrada:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

A palavra-chave `operation` começa a definição de operação, e é seguida pelo nome; aqui, `BitFlip` .
Em seguida, o tipo de entrada é definido como `Qubit` , juntamente com um nome `target` para se referir à entrada dentro da nova operação.
Da mesma forma, `Unit` define que a saída da operação está vazia.
Isto é usado da mesma forma `void` em C# e outras línguas imperativas, e é equivalente a `unit` em F# e outras línguas funcionais.

As operações também podem devolver tipos mais interessantes do que `Unit` .
Por exemplo, a <xref:microsoft.quantum.intrinsic.m> operação devolve uma saída do `Result` tipo, representando ter efetuado uma medição. Podemos passar a saída de uma operação para outra operação, ou podemos usá-la com a `let` palavra-chave para definir uma nova variável.

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
> Cada operação em Q# requer exatamente uma entrada e devolve exatamente uma saída.
> Várias entradas e saídas são então representadas usando *tuples,* que recolhem múltiplos valores juntos num único valor.
> Informalmente, dizemos que Q# é uma linguagem "tuple-in tuple-out".
> Seguindo este conceito, `()` deve então ser lido como o tuple "vazio", que tem o tipo `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Operações controladas e adjacentes

Se uma operação implementar uma transformação unitária, como é o caso de muitas operações em Q#, então é possível definir como a operação funciona quando *contígua* ou *controlada*. Uma especialização *adjacente* de uma operação especifica como o "inverso" da operação atua, enquanto uma especialização *controlada* especifica como uma operação age quando a sua aplicação está condicionada ao estado de um determinado registo quântico.

Os contíguos das operações quânticas são cruciais para muitos aspetos da computação quântica. Mais abaixo, na secção [Conjugações,](#conjugations) encontrará uma dessas situações discutida ao lado de uma técnica de programação Q# útil.

A versão controlada de uma operação é uma nova operação que aplica efetivamente a operação base apenas se todos os qubits de controlo estiverem num estado especificado.
Se os qubits de controlo estiverem em sobreposição, então a operação de base é aplicada de forma coerente à parte apropriada da sobreposição.
Assim, as operações controladas são frequentemente usadas para gerar emaranhados.

Naturalmente, também poderia existir uma especialização *adjacente controlada,* especificando a aplicação controlada do adjacente de uma operação.

> [!NOTE]
> Se $U$ é a transformação unitária implementada por uma `U` operação, então `Adjoint U` representa a transformação unitária $U^\dagger$, que é a transposição conjugada complexa.
> Aplicar sucessivamente uma operação e, em seguida, o seu contíguo a um estado deixa o estado inalterado, como ilustrado pelo facto de $UU^\dagger = U^\dagger U = \id$, a matriz de identidade.
> A representação unitária de uma operação controlada é um pouco mais matizada, mas pode encontrar mais detalhes em [conceitos de computação quântica: múltiplos qubits](xref:microsoft.quantum.concepts.multiple-qubits).

A secção seguinte descreve como chamar estas várias especializações no seu código Q#.
Abaixo, detalhamos como definir operações para as apoiar.

### <a name="calling-operation-specializations"></a>Especializações de operação de chamada

Um *functor* em Q# é uma fábrica que define uma nova operação a partir de outra operação.
Os dois funtores padrão em Q# são `Adjoint` e `Controlled` .

Os funtores têm acesso à implementação da operação base ao definir a implementação da nova operação.
Assim, os funtores podem desempenhar funções mais complexas do que as funções tradicionais de alto nível. Os functors não têm representação no sistema do tipo Q. Não é, portanto, atualmente possível ligá-los a uma variável ou passá-las como argumentos. 

Um functor é usado aplicando-o a uma operação, devolvendo uma nova operação.
Por exemplo, a operação que resulta da aplicação do `Adjoint` functor à `Y` operação é escrita como `Adjoint Y` .
A nova operação pode então ser invocada como qualquer outra operação.
Para uma operação de apoio à aplicação dos `Adjoint` e/ou `Controlled` funtores, o seu tipo de devolução tem necessariamente de ser `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`functor

Assim, `Adjoint Y(q1)` aplica o functor adjacente à `Y` operação para gerar uma nova operação, e aplica essa nova operação a `q1` .
A nova operação tem a mesma assinatura e tipo que a operação `Y` base.
Em particular, a nova operação também permite `Adjoint` , e permitirá `Controlled` se e somente se a operação base o fizer.
O functor adjoint é o seu próprio inverso; ou seja, `Adjoint Adjoint Op` é sempre o mesmo `Op` que. .

#### <a name="controlled-functor"></a>`Controlled`functor

Da mesma forma, `Controlled X(controls, target)` aplica o functor controlado à `X` operação para gerar uma nova operação, e aplica essa nova operação a `controls` e `target` .

> [!NOTE]
> Em Q#, as versões controladas tomam sempre uma série de qubits de controlo, e o estado especificado é sempre para que todos os qubits de controlo estejam no estado computacional `PauliZ` ( ) `One` {1}
> O controlo baseado noutros Estados pode ser alcançado aplicando a operação unitária adequada aos qubits de controlo antes da operação controlada e, em seguida, aplicando os inversos da operação unitária após a operação controlada.
> Por exemplo, aplicar uma `X` operação a um qubit de controlo antes e depois de uma operação controlada fará com que a `Zero` operação controle o estado ($\ket {0} $) para esse qubit; aplicando uma `H` operação antes e depois controlará o `PauliX` `One` estado, ou seja, -1 eigenvalue de Pauli X, $\ket {-} \mathrel{:=} {0} (\ket - \ket {1} ) / \sqrt {2} $ em vez do `PauliZ` `One` estado.

Dada a expressão da operação, pode formar-se uma nova expressão de operação utilizando o `Controlled` functor.
A assinatura da nova operação baseia-se na assinatura da operação original.
O tipo de resultado é o mesmo, mas o tipo de entrada é um dois tuple com uma matriz qubit que mantém o(s) qubit de controlo como primeiro elemento e os argumentos da operação original como segundo elemento.
A nova operação suporta `Controlled` , e irá suportar se e `Adjoint` somente se a operação original o fizer.

Se a operação original teve apenas um argumento, então a equivalência de tuple singleton entrará em jogo aqui.
Por exemplo, `Controlled X` é a versão controlada da `X` operação. 
`X`tem `(Qubit => Unit is Adj + Ctl)` tipo, assim `Controlled X` tem `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` tipo; por causa da equivalência de tuple singleton, este é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Se a operação base levou vários argumentos, lembre-se de incluir os argumentos correspondentes da versão controlada da operação em parênteses para convertê-los em tuple.
Por exemplo, `Controlled Rz` é a versão controlada da `Rz` operação. 
`Rz`tem `((Double, Qubit) => Unit is Adj + Ctl)` tipo, assim `Controlled Rz` como o tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Assim, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (note os parênteses em torno `0.1, target` de ).

Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)` . Se um alvo deve ser controlado por 2 qubits de controlo (CCNOT), podemos usar `Controlled X([control1, control2], target)` a declaração.

#### `Controlled Adjoint` 

Os `Controlled` `Adjoint` funtores e funtores viajam, por isso não há diferença entre a aplicação `Controlled Adjoint Op` ou `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Definição de implementações controladas e adjacentes

Na primeira operação exemplos acima referidos, as operações `BitFlip` `DecodeSuperdense` foram definidas com assinaturas `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` e, respectivamente.
Tal como `DecodeSuperdense` as medições, não se trata de uma operação unitária e, portanto, não podem existir especializações não adjacentes controladas (recorde-se a exigência de tal operação `Unit` de devolução).
No entanto, como `BitFlip` simplesmente executa a operação unitária, <xref:microsoft.quantum.intrinsic.x> poderíamos tê-lo definido com ambas as especializações.

Aqui, detalhamos como incluir a existência de especializações nas suas declarações de operação Q#, dando-lhes assim a capacidade de chamar em conjunto com os `Adjoint` e/ou `Controlled` funtores.
Mais [abaixo,](#circumstances-for-validly-defining-specializations)descrevemos algumas das situações em que é válido ou não é válido declarar determinadas especializações.

As características de operação definem que tipos de funtores podem ser aplicados à operação declarada e que efeito têm. A existência destas especializações pode ser declarada como parte da assinatura da operação, nomeadamente através de uma anotação com as características de funcionamento: `is Adj` `is Ctl` ou, ou `is Adj + Ctl` .
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
Assim, podemos usar este para escrever o `DecodeSuperdense` exemplo acima de forma mais compacta, usando o adjacente de transformar o estado emaranhado de volta em um par de `PrepareEntangledPair` qubits não emaranhados:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

A anotação com as características de funcionamento na declaração é útil para garantir que o compilador gera automaticamente outras especializações com base na implementação padrão. 

Existem uma série de limitações importantes a considerar ao conceber operações para uso com funtores.
Mais criticamente, as especializações para uma operação que utiliza o valor de saída de qualquer outra operação *não podem* ser geradas automaticamente pelo compilador, uma vez que é ambíguo como reordenar as declarações de tal operação para obter o mesmo efeito.

Por conseguinte, muitas vezes é útil especificar explicitamente as várias implementações.

### <a name="explicitly-specifying-implementations"></a>Especificar explicitamente implementações

No caso de a implementação não poder ser gerada pelo compilador, pode ser explicitamente especificada. Tais declarações explícitas de especialização podem consistir numa diretiva de *geração* adequada ou numa implementação definida pelo utilizador.
Aqui fornecemos toda a gama de possibilidades, com exemplos a seguir.


#### <a name="explicit-specialization-declarations"></a>Declarações explícitas de especialização

As operações Q# podem conter as seguintes declarações explícitas de especialização:

- A `body` especialização especifica a implementação da operação sem funtores aplicados.
- A `adjoint` especialização especifica a implementação da operação com o `Adjoint` functor aplicado.
- A `controlled` especialização especifica a implementação da operação com o `Controlled` functor aplicado.
- A `controlled adjoint` especialização especifica a implementação da operação com os `Adjoint` funtores e `Controlled` funtores aplicados.
  Esta especialização também pode ser `adjoint controlled` nomeada, uma vez que os dois funtores viajam.


Uma especialização de operação consiste na etiqueta de especialização (por `body` exemplo, `adjoint` ou, etc.) seguida de uma das seguintes:

- Uma declaração explícita, como descrito abaixo.
- Uma *diretiva* que diz ao compilador *como* gerar a especialização, uma das seguintes:
  - `intrinsic`, o que indica que a especialização é fornecida pela máquina-alvo.
  - `distribute`, que pode ser usado com as `controlled` `controlled adjoint` especializações e especializações.
    Quando utilizado `controlled` com , indica que o compilador deve calcular a especialização aplicando-se a todas as `Controlled` operações no `body` .
    Quando utilizado `controlled adjoint` com , indica que o compilador deve calcular a especialização aplicando-se a todas as `Controlled` operações da `adjoint` especialização.
  - `invert`, o que indica que o compilador deve calcular a `adjoint` especialização invertendo a `body` , ou seja, invertendo a ordem de operações e aplicando o adjacente a cada um.
    Quando `adjoint controlled` utilizado, isto indica que o compilador deve calcular a especialização invertendo a `controlled` especialização.
  - `self`, para indicar que a especialização adjacente é a mesma que a `body` especialização.
    Isto é legal para as `adjoint` `adjoint controlled` especializações.
    Pois, `adjoint controlled` `self` implica que a `adjoint controlled` especialização é a mesma que a `controlled` especialização.
  - `auto`, para indicar que o compilador deve selecionar uma diretiva adequada a aplicar.
    `auto`não pode ser utilizado para a `body` especialização.

As diretivas e `auto` todos requerem um fecho do ponto de souco. `;`
A `auto` diretiva resolve a seguinte diretiva relativa à geração se for fornecida uma declaração `body` explícita:

- A `adjoint` especialização é gerada de acordo com a `invert` diretiva.
- A `controlled` especialização é gerada de acordo com a `distribute` diretiva.
- A `adjoint controlled` especialização é gerada de acordo com a diretiva `invert` se for dada uma declaração `controlled` explícita, mas não uma para , e não para `adjoint` `distribute` outras.

> [!TIP]   
> Se uma operação for auto-adjacente, especifique explicitamente a especialização adjacente ou a especialização adjacente controlada através da diretiva `self` de geração, a fim de permitir que o compilador utilize essa informação para fins de otimização.

Uma declaração de especialização contendo uma implementação definida pelo utilizador consiste num tuple de argumento seguido de um bloco de declaração com o código Q# que implementa a especialização.
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

O código `PrepareEntangledPair` acima, por exemplo, é equivalente ao código abaixo que contém declarações explícitas de especialização: 

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

Se o compilador não conseguir gerar automaticamente a implementação para uma determinada especialização, ou se uma implementação mais eficiente puder ser dada, então a implementação também pode ser definida manualmente.

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
No exemplo acima, `adjoint invert;` indica que a especialização adjacente deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjacente controlada deve ser gerada invertendo a implementação dada da especialização controlada.

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

É legal especificar uma operação sem versões adjacentes ou controladas. Por exemplo, as operações de medição não têm nenhuma, porque não são invertíveis ou controláveis.

Uma operação apoia os `Adjoint` e/ou `Controlled` functors se a sua declaração contiver uma declaração implícita ou explícita das respetivas especializações.

Uma especialização explicitamente declarada adjacente/controlada implica a existência de uma especialização adjacente/controlada. 

Para uma operação cujo corpo contenha ciclos de repetição até ao sucesso, desemote declarações, medições, declarações de devolução ou chamadas para outras operações que não suportem o `Adjoint` functor, gerando automaticamente uma especialização adjacente seguindo a `invert` diretiva ou `auto` diretiva não é possível.

Para uma operação cujo corpo contenha chamadas para outras operações que não suportem o `Controlled` functor, não é possível gerar automaticamente uma especialização controlada seguindo a `distribute` diretiva ou `auto` diretiva.

#### <a name="controlled-adjoint"></a>Controlado adjacente

A versão adjacente controlada de uma operação especifica como é implementada uma versão com controlo quântico do adjacente à operação.
É legal especificar uma operação sem versão adjacente controlada; por exemplo, as operações de medição não têm versão adjacente controlada porque não são controláveis nem invertíveis.

Uma especialização adjacente controlada para uma operação tem de existir se e somente se existir uma especialização adjacente e controlada. Nesse caso, infere-se a existência da especialização adjacente controlada e a especialização adequada é gerada pelo compilador se não tiver sido definida explicitamente qualquer implementação. 

Para uma operação cujo corpo contenha chamadas para outras operações que não tenham uma versão adjacente controlada, não é possível gerar automaticamente uma especialização adjacente na sequência da `invert` `distribute` , ou `auto` diretiva.


### <a name="type-compatibility"></a>Compatibilidade tipo

Uma operação com funtores adicionais suportados pode ser usada em qualquer lugar uma operação com menos funtores, mas a mesma assinatura é esperada.
Por exemplo, uma operação do tipo `(Qubit => Unit is Adj)` pode ser utilizada em qualquer lugar que seja esperada uma operação do `(Qubit => Unit)` tipo.

Q# é *covariante* no que diz respeito aos tipos de retorno callable: uma chamada que devolve um tipo `'A` é compatível com um chamado com o mesmo tipo de entrada e um tipo de resultado `'A` compatível com.

Q# é *contravariante* no que diz respeito aos tipos de entrada: uma chamada que toma um tipo `'A` como entrada é compatível com uma chamada com o mesmo tipo de resultado e um tipo de entrada compatível com `'A` .

Isto é, dadas as seguintes definições:

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

são verdadeiros:

- A função `ConjugateInvertWith` pode ser invocada com um `inner` argumento de qualquer um ou . `Invert` `ApplyUnitary` .
- A função `ConjugateUnitaryWith` pode ser invocada com um `inner` argumento `ApplyUnitary` de, mas não `Invert` .
- Um valor do tipo `(Qubit[] => Unit is Adj + Ctl)` pode ser devolvido de `ConjugateInvertWith` .

> [!IMPORTANT]
> Q. 0.3 introduziu uma diferença significativa no comportamento dos tipos definidos pelo utilizador.

Os tipos definidos pelo utilizador são tratados como uma versão embrulhada do tipo subjacente, em vez de como um subtipo.
Isto significa que um valor de um tipo definido pelo utilizador não é utilizável quando se espera um valor do tipo subjacente.


### <a name="conjugations"></a>Conjugações

Em contraste com os bits clássicos, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejáveis na computação restante se os qubits ainda estiverem emaranhados. Isto pode ser evitado "desfazendo" os cálculos realizados corretamente antes de libertar a memória. Um padrão comum na computação quântica é, por conseguinte, o seguinte: 

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

Começando com o nosso lançamento 0.9, apoiamos uma declaração de conjugação que implementa a transformação acima. Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:

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
Tal declaração de conjugação torna-se obviamente muito mais útil se a transformação exterior e interior não estiver prontamente disponível como operações, mas são mais convenientes para descrever por um bloco que consiste em várias declarações. 

A transformação inversa para as declarações definidas no bloco interior é gerada automaticamente pelo compilador e executada após o fim do bloco de aplicação.
Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente o adjacente do cálculo no bloco interior. 


## <a name="defining-new-functions"></a>Definição de Novas Funções

As funções são puramente determinísticas, rotinas clássicas em Q#, que são distintas das operações na qual não são permitidas a ter quaisquer efeitos além de calcular um valor de saída.
Em especial, as funções não podem convocar operações; agir, alocar ou pedir qubits emprestados; amostra de números aleatórios; ou de outra forma dependem do estado para além do valor de entrada para uma função.
Como consequência, as funções Q# são *puras,* na medida em que mapeiam sempre os mesmos valores de entrada para os mesmos valores de saída.
Isto permite que o compilador Q# reencomenda com segurança como e quando as funções são chamadas ao gerar especializações de operação.

Cada ficheiro de origem Q# pode definir qualquer número de funções.
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

Sempre que possível, é útil escrever lógica clássica em termos de funções e não de operações, para que possa ser mais facilmente utilizada a partir de operações.
Por exemplo, se tivéssemos escrito a `Square` declaração acima como uma *operação*, então o compilador não teria sido capaz de garantir que chamá-lo com a mesma entrada produziria consistentemente as mesmas saídas.

Para sublinhar a diferença entre funções e operações, considere o problema da amostragem clássica de um número aleatório dentro de uma operação Q# :

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Cada vez que `U` for chamado, terá uma ação `target` diferente.
Em particular, o compilador não pode garantir que, se adicionarmos uma `adjoint auto` declaração de `U` especialização, `U(target); Adjoint U(target);` então age como identidade (isto é, como um não-op).
Isto viola a definição do adjacente que vimos em [Vetores e Matrizes,](xref:microsoft.quantum.concepts.vectors)de tal forma que permitir gerar automaticamente uma especialização adjacente numa operação em que chamamos a operação <xref:microsoft.quantum.math.randomreal> quebraria as garantias fornecidas pelo compilador; é uma operação para a <xref:microsoft.quantum.math.randomreal> qual não existe nenhuma versão adjacente ou controlada.

Por outro lado, permitir chamadas de funções como `Square` é seguro, na medida em que o compilador pode ser assegurado que só precisa de preservar a entrada `Square` para manter a sua saída estável.
Assim, isolar o máximo de lógica clássica possível em funções torna fácil a reutilização dessa lógica noutras funções e operações.


## <a name="generic-type-parameterized-callables"></a>Caláveis genéricos (tipo-parametrizados)

Muitas funções e operações que podemos desejar definir não dependem fortemente dos tipos das suas entradas, mas apenas usam implicitamente os seus tipos através de outra função ou funcionamento.
Por exemplo, considere o conceito de *mapa* comum a muitas línguas funcionais; dada uma função $f(x)$ e uma coleção de valores $ \{ x_1, x_2, \dots, x_n \} $, o mapa devolve uma nova coleção $ \{ f(x_1), f(x_2), \dots, f(x_n) \} $.
Para implementar isto em Q#, podemos aproveitar que as funções são de primeira classe.
Vamos escrever um exemplo rápido de `Map` , usando ★ como espaço reservado enquanto descobrimos que tipos precisamos.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que esta função parece muito a mesma, independentemente dos tipos reais que substituamos.
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

Em princípio, poderíamos escrever uma versão `Map` de todos os tipos que encontramos, mas isto introduz uma série de dificuldades.
Por exemplo, se encontrarmos um `Map` bug, então temos de garantir que a correção é aplicada uniformemente em todas as versões de `Map` .
Além disso, se construirmos um novo tuple ou UDT, então temos agora também de construir um novo `Map` para acompanhar o novo tipo.
Embora isto seja tratável para um pequeno número de tais funções, à medida que recolhemos cada vez mais funções da mesma forma `Map` que, o custo de introdução de novos tipos torna-se irracionalmente grande em ordem bastante curta.

Grande parte desta dificuldade resulta, no entanto, daí não termos dado ao compilador a informação de que necessita para reconhecer como as diferentes versões `Map` estão relacionadas.
Efetivamente, queremos que o compilador trate `Map` como algum tipo de função matemática, desde os *tipos* Q# até às funções Q#.

Esta noção é formalizada permitindo que funções e operações tenham *parâmetros de tipo,* bem como os seus parâmetros comuns de tuple.
Nos exemplos acima referidos, gostaríamos de pensar que `Map` temos parâmetros de tipo no primeiro e no segundo `Int, Pauli` `Double, String` caso.
Na maior parte dos casos, estes parâmetros de tipo podem então ser usados como se fossem tipos comuns: usamos valores de parâmetros de tipo para fazer matrizes e tuples, funções de chamada e operações, e atribuir a variáveis comuns ou mutáveis.

> [!NOTE]
> O caso mais extremo de dependência indireta é o dos qubits, onde um programa Q# não pode depender diretamente da estrutura do `Qubit` tipo, mas **deve** passar esses tipos para outras operações e funções.

Voltando ao exemplo acima, então, podemos ver que precisamos de `Map` ter parâmetros de tipo, um para representar a entrada `fn` e outro para representar a saída de `fn` .
Em Q#, isto é escrito adicionando suportes de ângulo (isto `<>` é, não trava $\braket {} $!) após o nome de uma função ou operação na sua declaração, e enumerando cada parâmetro do tipo.
O nome de cada parâmetro do tipo deve começar com um `'` carrapato, indicando que se trata de um parâmetro do tipo e não de um tipo comum (também conhecido como tipo *de betão).*
Pois, `Map` assim, escrevemos:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Note que a definição de `Map<'Input, 'Output>` parece extremamente semelhante às versões que escrevemos antes.
A única diferença é que informamos explicitamente o compilador que `Map` não depende diretamente do que `'Input` e `'Output` são, mas funciona para qualquer dois tipos, utilizando-os indiretamente através `fn` de .
Uma vez definido `Map<'Input, 'Output>` desta forma, podemos chamá-lo como se fosse uma função comum:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Escrever funções genéricas e operações é um lugar onde "tuple-in tuple-out" é uma forma muito útil de pensar sobre funções e operações Q#.
> Uma vez que cada função requer exatamente uma entrada e devolve exatamente uma saída, uma entrada de tipo `'T -> 'U` corresponde a *qualquer* função Q#.
> Da mesma forma, qualquer operação pode ser transmitida a uma entrada do tipo `'T => 'U` .

Como segundo exemplo, considere o desafio de escrever uma função que devolve a composição de duas outras funções:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Aqui, temos de especificar exatamente o `A` `B` que, e `C` estamos, portanto, a limitar severamente a utilidade da nossa nova `Compose` função.
Afinal, `Compose` só depende `A` de `B` , e `C` *via* `innerFn` e `outerFn` .
Como alternativa, então, podemos adicionar parâmetros de tipo `Compose` a que indicam que funciona para *qualquer* , e , desde que `A` estes `B` `C` parâmetros correspondam aos esperados por `innerFn` `outerFn` e:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

As bibliotecas padrão Q# fornecem uma gama de operações e funções por tipo-parametrizadas para facilitar a expressão do fluxo de controlo de ordem superior.
Estes são discutidos mais adiante no [guia da biblioteca padrão Q#](xref:microsoft.quantum.libraries.standard.intro).


## <a name="callables-as-first-class-values"></a>Calíveis como Valores de Primeira Classe

Uma técnica crítica para o raciocínio sobre o fluxo de controlo e a lógica clássica utilizando funções em vez de operações é utilizar que as operações e funções em Q# são *de primeira classe*.
Ou seja, são valores cada um na língua por direito próprio.
Por exemplo, o seguinte é perfeitamente válido código Q#, se um pouco indireto:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

O valor da variável `ourH` no corte acima é então a operação , de modo que <xref:microsoft.quantum.intrinsic.h> podemos chamar esse valor como qualquer outra operação.
Isto permite-nos escrever operações que tomem operações como parte da sua entrada, formando conceitos de fluxo de controlo de ordem superior.
Por exemplo, podemos imaginar querer "quadrar" uma operação aplicando-a duas vezes ao mesmo qubit alvo.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>Operações de regresso de uma função

Sublinhamos que também podemos devolver operações como parte das saídas, de modo a que possamos isolar alguns tipos de lógica condicional clássica como uma função clássica que devolve uma descrição de um programa quântico sob a forma de uma operação.
Como exemplo simples, considere o exemplo de teletransporte, no qual o partido que recebe uma mensagem clássica de duas partes precisa de usar a mensagem para descodificar o seu qubit no estado teletransportado adequado.
Poderíamos escrever isto em termos de uma função que pega nessas duas partes clássicas e devolve a operação de descodição adequada.

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

Esta nova função é de facto uma função, na qual se chamá-la com os mesmos valores de `hereBit` `thereBit` e, vamos sempre recuperar a mesma operação.
Assim, o descodificador pode ser executado com segurança dentro de operações sem ter que raciocinar sobre como a lógica de descodificante interage com as definições das diferentes especializações de operação.
Ou seja, isolamos a lógica clássica dentro de uma função, garantindo ao compilador que a chamada de função pode ser reordenada com impunidade enquanto a entrada for preservada.


## <a name="partial-application"></a>Aplicação Parcial

Podemos fazer significativamente mais com funções que devolvem as operações usando *a aplicação parcial,* na qual podemos fornecer uma ou mais partes da entrada para uma função ou operação sem realmente chamá-lo. Por exemplo, recordando o `ApplyTwice` exemplo acima, podemos indicar que não queremos especificar, imediatamente, a que qubit deve aplicar a operação de entrada:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Neste caso, a variável local `twiceOp` detém a operação parcialmente `ApplyTwice(op, _)` aplicada, onde partes da entrada que ainda não foram especificadas são indicadas por `_` .
Quando realmente chamamos `twiceOp` na linha seguinte, passamos como entrada para a operação parcialmente aplicada todas as partes restantes da entrada para a operação original.
Assim, o corte acima é efetivamente idêntico a ter chamado `ApplyTwice(op, target)` diretamente, salvo para isso introduzimos uma nova variável local que nos permite atrasar a chamada enquanto fornecemos algumas partes da entrada.

Uma vez que uma operação que foi parcialmente aplicada não é realmente chamada até que toda a sua entrada tenha sido fornecida, podemos aplicar parcialmente as operações de forma segura mesmo a partir de funções.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Em princípio, a lógica clássica dentro de si `SquareOperation` poderia ter sido muito mais envolvida, mas ainda está isolada do resto de uma operação pelas garantias que o compilador pode oferecer sobre funções.
Esta abordagem será usada em toda a biblioteca padrão Q# para expressar o fluxo de controlo clássico de uma forma que pode ser facilmente usada dentro de programas quânticos.


## <a name="recursion"></a>Recursão

Q# os callables podem ser direta ou indiretamente recursivos.
Ou seja, uma operação ou função pode chamar-se a si mesma, ou pode chamar outra chamada que, direta ou indiretamente, chama a operação callable.

No entanto, existem dois comentários importantes sobre a utilização da recursão:

- A utilização de recursões nas operações é suscetível de interferir com determinadas otimizações.
  Isto pode ter um impacto substancial no tempo de execução do algoritmo.
- Ao executar um dispositivo quântico real, o espaço da pilha pode ser limitado, e assim a recursão profunda pode levar a um erro de tempo de execução.
  Em particular, o compilador Q# e o tempo de execução não identificam e otimizam a recursão da cauda.

## <a name="next-steps"></a>Próximos passos

Saiba mais [sobre variáveis](xref:microsoft.quantum.guide.variables) em Q#.