---
title: Modelo tipo Q# [ modelo] Microsoft Docs
description: Modelo de tipo Q#
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0aabb144779da301b71ad215c8e975cc29b4dcce
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76871639"
---
# <a name="the-type-model"></a>O Modelo Tipo

Esta secção estabelece o modelo do tipo Q# e descreve a sintaxe para especificar e trabalhar com tipos.
Notamos que q# é uma linguagem *fortemente dactilografada,* de tal forma que uma utilização cuidadosa destes tipos pode ajudar o compilador a fornecer fortes garantias sobre os programas Q# no momento da compilação.

A fim de fornecer as garantias mais fortes possíveis, as conversões entre tipos em Q# devem ser explícitas utilizando chamadas para funções que expressem essa conversão. Uma variedade dessas funções são fornecidas como parte do espaço de nome <xref:microsoft.quantum.convert>.
As upcasts para tipos compatíveis, por outro lado, acontecem implicitamente. 

Q# fornece ambos os tipos primitivos, que podem ser usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.
Descrevemos cada um no resto desta secção.

## <a name="primitive-types"></a>Tipos Primitivos

A língua Q# fornece vários *tipos primitivos,* a partir dos quais outros tipos podem ser construídos:

- O tipo `Int` representa um inteiro assinado de 64 bits, por exemplo: `2`, `107`, `-5`.
- O tipo `BigInt` representa um inteiro assinado de tamanho arbitrário, por exemplo, `2L`, `107L`, `-5L`.
   Este tipo baseia-se no <xref:System.Numerics.BigInteger> .NET
   tipo.
- O tipo `Double` representa um número de ponto flutuante de dupla precisão, por exemplo: `0.0`, `-1.3`, `4e-7`.
- O tipo `Bool` representa um valor booleano que pode ser `true` ou `false`.
- O tipo `Qubit` representa um bit quântico ou qubit.
   `Qubit`são opacos para o utilizador; a única operação possível com eles, para além de os passar para outra operação, é testar a identidade (igualdade).
   Em última análise, as ações em `Qubit`s são implementadas chamando instruções intrínsecas num processador quântico (ou uma simulação do mesmo).
- O tipo `Pauli` representa um dos quatro operadores pauli de um único qubit.
   Este tipo é utilizado para denotar o funcionamento da base para rotações e para especificar o observável que está a ser medido.
   Este é um tipo enumerado que tem quatro valores possíveis: `PauliI`, `PauliX`, `PauliY`e `PauliZ`, que são constantes de tipo `Pauli`.
- O `Result` tipo representa o resultado de uma medição.
   Este é um tipo enumerado com dois valores possíveis: `One` e `Zero`, que são constantes de tipo `Result`.
   `Zero` indica que o valor +1 foi medido; `One` indica o valor de -1.
- O tipo `Range` representa uma sequência de inteiros, denotados por `start..step..stop`, onde denotar o passo são opções. 
   Isto é `start .. stop` corresponde a `start..1..stop`, e, por exemplo, `1..2..7` representa a sequência de $\{1, 3, 5, 7\}$.
- O tipo `String` é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.
  Este tipo é usado para relatar mensagens a um hospedeiro clássico em caso de erro ou evento de diagnóstico.
- O tipo `Unit` é do tipo que permite apenas um valor `()`. 
  Este tipo é utilizado para indicar que a função ou operação Q# não devolve nenhuma informação. 

As constantes `true`, `false`, `PauliI`, `PauliX``PauliY`, `PauliZ`, `One`e `Zero` são símbolos reservados em Q#.

## <a name="array-types"></a>Tipos de matriz

Dado qualquer `'T`de tipo Q# válido, existe um tipo que representa uma matriz de valores de tipo `'T`.
Este tipo de matriz é representado como `'T[]`; por exemplo, `Qubit[]` ou `Int[][]`.
Por exemplo, uma coleção de inteiros é denotada `Int[]`, enquanto uma série de conjuntos de valores `(Bool, Pauli)` é denotado `(Bool, Pauli)[][]`.

No segundo exemplo, note que isto representa uma matriz potencialmente irregular de matrizes, e não uma matriz bidimensional retangular.
Q# não fornece suporte para matrizes multidimensionais retangulares.

Um valor de matriz pode ser escrito no código fonte Q# utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]`.
O tipo de matriz literal é determinado pelo tipo de base comum de todos os itens da matriz. 

> [!WARNING]
> Os elementos de uma matriz não podem ser alterados após a criação da matriz.
> As declarações de atualização e reatribuição e/ou expressões de cópia e atualização podem ser utilizadas para construir uma matriz modificada.

Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a palavra-chave `new`:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Em qualquer dos casos, uma vez construída uma matriz, a função central `Length` pode ser utilizada para obter o número de elementos como `Int`.
As matrizes podem ser subscritas utilizando suportes quadrados, com subscripts com tipo `Int` ou tipo `Range`, para obter elementos únicos ou novas matrizes contendo um subconjunto dos elementos de uma matriz.
Os subscripts de matrizes são baseados em zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipos de tuple

Tendo em conta os tipos zero ou mais diferentes `T0`, `T1`, ..., `Tn`, podemos notar um novo tipo de *tuple* como `(T0, T1, ..., Tn)`.
Os tipos utilizados para construir um novo tipo de tuple podem ser por si mesmos tuples, como em `(Int, (Qubit, Qubit))`.
No entanto, esta nidificação é sempre finita, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.

Os valores do novo tipo de tuple são tuples formados por sequências de valores de cada tipo na tuple.
Por exemplo, `(3, false)` é uma tuple cujo tipo é o tipo de tuple `(Int, Bool)`.
É possível criar conjuntos de tuples, tuples de matrizes, tuples de sub-tuples, etc.

A partir do Q#0.3, `Unit` é o nome do *tipo* de tuple vazio; `()` é utilizado para o *valor*vazio do tuple .

Os casos de tuple são imutáveis.
Q# não fornece um mecanismo para alterar o conteúdo de uma tuple uma vez criado.

Tuples são um conceito poderoso usado ao longo de Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.
Em particular, usando a notação de tuple, podemos expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.

### <a name="singleton-tuple-equivalence"></a>Equivalência singleton Tuple

É possível criar uma tuple singleton (elemento único), `('T1)`, como `(5)` ou `([1,2,3])`.
No entanto, Q# trata uma túnica singleton como completamente equivalente a um valor do tipo fechado.
Ou seja, não há diferença entre `5` e `(5)`, ou entre `5` e `(((5)))`, ou entre `(5, (6))` e `(5, 6)`.

Esta equivalência aplica-se a todos os fins, incluindo atribuição e expressões.
É igualmente válido escrever `(5)+3` como escrever `5+3`, e ambas as expressões avaliarão para `8`.
Isto significa, em particular, que uma operação ou função cujo tipo de tuple de entrada ou tuple de saída tem um campo pode ser considerado como tendo um único argumento ou devolvendo um único valor.

Referimo-nos a esta propriedade como _equivalência de tuple singleton._

## <a name="user-defined-types"></a>Tipos definidos pelo utilizador

Um ficheiro Q# pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.
Para qualquer tipo de `T`, podemos declarar um novo tipo definido pelo utilizador que é um subtipo de `T` com a declaração `newtype`.
No espaço de nome @"microsoft.quantum.math", por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:

```qsharp
newtype Complex = (Double, Double);
```

Esta afirmação cria um novo tipo com dois itens anónimos de tipo `Double`.   
Além de itens anónimos, os tipos definidos pelo utilizador também suportam itens nomeados a partir da versão Q# 0.7 ou superior. Por exemplo, poderíamos ter nomeado os itens `Re` para o duplo que representa a parte real de um número complexo e `Im` para a parte imaginária: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportado. Além disso, também podem ser nomeados itens internos.
O tipo `Nested` como definido abaixo, por exemplo, tem um tipo subjacente `(Double, (Int, String))`, dos quais apenas o item de tipo `Int` é nomeado e todos os outros itens são anónimos. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Os itens nomeados têm a vantagem de poderem ser acedidos diretamente através do operador de acesso `::`. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Para aceder a itens anónimos, por outro lado, o valor embrulhado primeiro precisa de ser extraído utilizando o operador de pós-fixação `!`.
O operador "desembrulhar", `!`, permite extrair o valor contido num tipo definido pelo utilizador.
O tipo de expressão "desembrulhar" é o tipo subjacente do tipo definido pelo utilizador. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

O operador desembrulhar desembrulha exatamente uma camada de embrulho.
Vários operadores de desembrulhar podem ser utilizados para aceder a um valor embrulhado multiplicado.

Por exemplo:

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

Veja a secção sobre [expressões desembrulhadas](xref:microsoft.quantum.language.expressions#unwrap-expressions) e precedência dos [operadores](xref:microsoft.quantum.language.expressions#operator-precedence) para mais detalhes.

Os valores de um tipo definido pelo utilizador podem ser criados chamando o construtor de tipo correspondente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternativamente, novos valores podem ser criados a partir dos existentes usando [expressões de cópia e atualização](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Tal como para as matrizes, tais expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados. Para estes, os valores são definidos para os definidos no lado direito da expressão. Quaisquer outras construções linguísticas, como, por exemplo, [declarações de atualização e reatribuição,](xref:microsoft.quantum.language.statements#update-and-reassign-statement)que estejam disponíveis para itens de matriz, existem também para itens nomeados em tipos definidos pelo utilizador.

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

Os tipos definidos pelo utilizador podem ser utilizados em qualquer outro tipo.
Em particular, é possível definir um conjunto de um tipo definido pelo utilizador e incluir um tipo definido pelo utilizador como um elemento de um tipo de tuple.

Não é possível criar estruturas de tipo recursivos.
Ou seja, o tipo que define um tipo definido pelo utilizador pode não ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.
De um modo mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas entre si, pelo que o seguinte conjunto de definições de tipo seria ilegal:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Além de fornecer pseudónimos curtos para tipos de tuple potencialmente complicados, uma vantagem significativa de definir tais tipos é que eles podem documentar a intenção de um valor particular.
Voltando ao exemplo de `Complex`, também se poderia ter definido as coordenadas polares 2D como um tipo definido pelo utilizador:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Apesar de ambos `Complex` e `Polar` terem um tipo subjacente `(Double, Double)`, os dois tipos são totalmente incompatíveis em Q#, minimizando o risco de chamar acidentalmente uma função matemática complexa com coordenadas polares e vice-versa.
Desta forma, os tipos definidos pelo utilizador F# têm um papel semelhante ao dos Registos, por exemplo. 


## <a name="operation-and-function-types"></a>Tipos de Funcionamento e Função

Uma _operação_ Q# é uma subrotina quântica.
Ou seja, é uma rotina que pode ser chamada que contém operações quânticas.

Uma _função_ Q# é uma subrotina clássica usada dentro de um algoritmo quântico.
Pode conter código clássico, mas sem operações quânticas.
Especificamente, as funções não podem alocar ou emprestar qubits, nem podem chamar operações.
No entanto, é possível passar-lhes operações ou qubits para processamento.
As funções são, portanto, inteiramente determinísticas no sentido de que chamá-las com os mesmos argumentos produzirá sempre o mesmo resultado. 

Em conjunto, as operações e funções são chamadas _de callables_.  Pode ver [alguns exemplos destes](#examples) abaixo.

Todos os callables Q# são considerados como tendo um único valor como entrada e devolver um único valor como saída.
Tanto os valores de entrada como de saída podem ser tuples.
Callables que não têm resultado retorno `Unit`.
Os inputáveis que não têm entrada tomam a túnica vazia como entrada.

O tipo básico para qualquer callable é escrito como `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)`, onde tanto `'Tinput` como `'Tresult` são tipos.
A primeira forma, com `=>`, é utilizada para operações; a segunda forma, com `->`, para funções.
Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura para uma possível operação de medição de qubit único.

Os tipos de funções são completamente especificados pela sua assinatura.
Por exemplo, uma função que computa o seno de um ângulo teria tipo `(Double -> Double)`.

As operações — mas não as funções — têm certas características adicionais que são _expressas_ como parte do tipo de operação. Estas características incluem informações sobre os functores que a operação suporta.
Os functores são meta-operações que geram uma especialização de uma operação base; ver [Functors,](#functors)abaixo.

Os tipos de funcionamento são especificados pelo seu tipo de entrada, tipo de saída e suas características.    
Para exigir apoio para o `Controlled` e/ou `Adjoint` functor num tipo de operação, precisamos adicionar uma anotação indicando as características correspondentes.
Uma anotação `is Ctl` por exemplo indica que a operação é controlável. Se quisermos exigir que uma operação desse tipo suporte tanto o `Adjoint` como o functor `Controlled` podemos expressar isto como `(Qubit => Unit is Adj + Ctl)`. As características de funcionamento utilizadas `Adj` e `Ctl` estritamente falando são dois conjuntos de etiquetas pré-definidos, em que cada rótulo indica características de funcionamento específicas, como, por exemplo, o suporte a um functor específico.
Assim, `+` é usado para indicar a união desses dois conjuntos, e `*` é usado para indicar o cruzamento - isto é, os rótulos que são comuns a ambos os conjuntos.  

Por exemplo, a operação `X` Pauli tem tipo `(Qubit => Unit is Adj + Ctl)`.
Um tipo de funcionamento que não suporta functores é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.


### <a name="type-parameterized-functions-and-operations"></a>Funções e operações parametrizadas tipo

Os tipos de callable podem conter parâmetros de tipo.
Os parâmetros do tipo são indicados por um símbolo prefixado por uma única citação; por exemplo, `'A` é um parâmetro de tipo legal.

Um parâmetro de tipo pode aparecer mais de uma vez numa única assinatura.
Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e devolve os resultados recolhidos teria assinatura `(('A[], 'A->'A) -> 'A[])`.
Da mesma forma, uma função que desliga a composição de duas operações pode ter assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.

Ao invocar um tipo de escala tometável, todos os argumentos que tenham o mesmo parâmetro devem ser do mesmo tipo.

Q# não fornece um mecanismo para limitar os tipos possíveis que podem ser substituídos por um parâmetro de tipo.

### <a name="type-compatibility"></a>Compatibilidade tipo

Uma operação com functores adicionais suportados pode ser usada em qualquer lugar de uma operação com menos functores, mas a mesma assinatura é esperada.
Por exemplo, uma operação de tipo `(Qubit => Unit is Adj)` pode ser utilizada em qualquer lugar que se espere uma operação de tipo `(Qubit => Unit)`.

Q# é covariante em relação aos tipos de retorno caltáveis: um callable que devolve um tipo `'A` é compatível com um callable com o mesmo tipo de entrada e um tipo de resultado com o qual `'A` é compatível.

Q# é contravariante em relação aos tipos de entrada: um callable que leva um tipo `'A` pois a entrada é compatível com uma chamada com o mesmo tipo de resultado e um tipo de entrada compatível com `'A`.

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

- A função `ConjugateInvertWith` pode ser invocada com um argumento `inner` de `Invert` ou `ApplyUnitary`.
- A função `ConjugateUnitaryWith` pode ser invocada com um argumento `inner` de `ApplyUnitary`, mas não `Invert`.
- Um valor de `(Qubit[] => Unit is Adj + Ctl)` tipo pode ser devolvido de `ConjugateInvertWith`.

> [!IMPORTANT]
> Q# 0.3 introduz uma diferença significativa no comportamento dos tipos definidos pelo utilizador.

Os tipos definidos pelo utilizador são tratados como uma versão embrulhada do tipo subjacente, em vez de como um subtipo.
Isto significa que um valor de um tipo definido pelo utilizador não é utilizável quando se espera um valor do tipo subjacente.

### <a name="functors"></a>Functores

Um functor em Q# é uma fábrica que define uma nova operação a partir de outra operação.
Os functores têm acesso à implementação da operação base na definição da implementação da nova operação.
Assim, os functores podem desempenhar funções mais complexas do que as funções tradicionais de alto nível.

Os functores não têm representação no sistema do tipo Q#. Por conseguinte, não é atualmente possível ligá-los a uma variável ou aprová-los como argumentos. 

Um functor é utilizado aplicando-o a uma operação, devolvendo uma nova operação.
Por exemplo, a operação que resulta da aplicação do functor `Adjoint` à operação `Y` é escrita como `Adjoint Y`.
A nova operação pode então ser invocada como qualquer outra operação.
Assim, `Adjoint Y(q1)` aplica o functor Adjoint à operação `Y` para gerar uma nova operação, e aplica essa nova operação para `q1`.

Do mesmo modo, `Controlled X(controls, target)` aplica o functor controlado à operação `X` para gerar uma nova operação, e aplica essa nova operação para `controls` e `target`.

Os dois functores padrão em Q# são `Adjoint` e `Controlled`.

#### <a name="adjoint"></a>Adjoint

Na computação quântica, a adjoint de uma operação é a complexa transposição conjugada da operação.
Para operações que implementem um operador unitário, o adjoint é o inverso da operação.
Para uma operação simples que apenas invoque uma sequência de outras operações unitárias num conjunto de qubits, o adjoint pode ser calculado aplicando as juntas de anúncios das suboperações nos mesmos qubits, na sequência inversa.

Dada a expressão de operação, pode ser formada uma nova expressão de operação utilizando o functor `Adjoint`.
Por exemplo, `Adjoint QFT` designa o adjoint da operação `QFT`.
A nova operação tem a mesma assinatura e tipo que a operação base.
Em particular, a nova operação também permite `Adjoint`, e permitirá `Controlled` se e apenas se a operação base o fizesse.

O functor Adjoint é o seu próprio inverso; isto é, `Adjoint Adjoint Op` é sempre o mesmo que `Op`.

#### <a name="controlled"></a>Controlado

A versão controlada de uma operação é uma nova operação que aplica eficazmente o funcionamento da base apenas se todos os qubits de controlo estiverem num estado determinado.
Se os qubits de controlo estiverem em sobreposição, então o funcionamento da base é aplicado de forma coerente à parte adequada da superposição.
Assim, as operações controladas são frequentemente usadas para gerar emaranhado.

Em Q#, as versões controladas tomam sempre uma série de qubits de controlo, e o estado especificado é sempre para todos os qubits de controlo estarem no estado computacional (`PauliZ``One` ), $\ket{1}$.
O controlo baseado noutros Estados pode ser alcançado aplicando a operação unitária adequada aos qubits de controlo antes da operação controlada e aplicando os inversos da operação unitária após a operação controlada.
Por exemplo, a aplicação de uma operação `X` a um qubit de controlo antes e depois de uma operação controlada fará com que a operação controle o estado `Zero` ($\ket{0}$) para esse qubit; aplicação de uma operação `H` antes e depois controlará o `PauliX` estado `One`, ou seja, -1 eigenvalue de Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ em vez do `PauliZ` estado `One`.

Dada a expressão de operação, pode ser formada uma nova expressão de operação utilizando o functor `Controlled`.
A assinatura da nova operação baseia-se na assinatura da operação original.
O tipo de resultado é o mesmo, mas o tipo de entrada é um dois tuple com uma matriz qubit que detém o qubit de controlo como primeiro elemento e os argumentos da operação original como segundo elemento.
A nova operação apoia `Controlled`, e apoiará `Adjoint` se e apenas se a operação original o fizesse.

Se a operação original teve apenas um único argumento, então a equivalência de tuple singleton entrará em jogo aqui.
Por exemplo, `Controlled X` é a versão controlada da operação `X`.
`X` tem `(Qubit => Unit is Adj + Ctl)`tipo, por isso `Controlled X` tem `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`tipo; por causa da equivalência de tuple singleton, este é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Se a operação base tomou vários argumentos, lembre-se de encerrar os argumentos correspondentes da versão controlada da operação em parênteses para convertê-los em um tuple.
Por exemplo, `Controlled Rz` é a versão controlada da operação `Rz`.
`Rz` tem `((Double, Qubit) => Unit is Adj + Ctl)`tipo, por isso `Controlled Rz` tem `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`tipo.
Assim, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (note os parênteses em torno `0.1, target`).

Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)`. Se um alvo deve ser controlado por 2 qubits de controlo (CCNOT), podemos usar `Controlled X([control1, control2], target)` declaração.

### <a name="examples"></a>Exemplos

Este exemplo de uma operação Q# provém da amostra [de medição.](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) No âmbito das operações, podemos alocar qubits e utilizar operações quânticas nesses qubits, tais como `H` e `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

Este exemplo de função provém da amostra de Estimativa de [Fase.](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) Contém código puramente clássico. Pode ver que, ao contrário do exemplo acima, não são atribuídos qubits, e não são utilizadas operações quânticas.

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Também é possível que uma função seja passada qubits para processamento, como neste exemplo a partir da amostra [ReversívelLogicSynthesis.](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) Os qubits são passados para a função e usados para o processamento, embora em nenhum momento os próprios estados qubit sejam modificados.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
