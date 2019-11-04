---
title: 'Modelo de tipo Q # | Microsoft Docs'
description: 'Modelo de tipo Q #'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184751"
---
# <a name="the-type-model"></a>O modelo de tipo

Esta seção apresenta o modelo de tipo Q # e descreve a sintaxe para especificar e trabalhar com tipos.
Observe que Q # é uma linguagem *fortemente tipada* , de modo que o uso cuidadoso desses tipos pode ajudar o compilador a fornecer fortes garantias sobre programas do Q # no momento da compilação.

Para fornecer as garantias mais fortes possíveis, as conversões entre os tipos em Q # devem ser explícitas usando chamadas para funções que expressam essa conversão. Uma variedade dessas funções é fornecida como parte do namespace <xref:microsoft.quantum.convert>.
Os upcasts para tipos compatíveis, por outro lado, acontecem implicitamente. 

O Q # fornece os dois tipos primitivos, que podem ser usados diretamente e várias maneiras de produzir novos tipos de outros tipos.
Descrevemos cada um no restante desta seção.

## <a name="primitive-types"></a>Tipos primitivos

A linguagem Q # fornece vários *tipos primitivos*, dos quais outros tipos podem ser construídos:

- O tipo de `Int` representa um inteiro com sinal de 64 bits, por exemplo: `2`, `107``-5`.
- O tipo de `BigInt` representa um inteiro assinado de tamanho arbitrário, por exemplo, `2L`, `107L``-5L`.
   Esse tipo é baseado no .NET <xref:System.Numerics.BigInteger>
   Escreva.
- O tipo de `Double` representa um número de ponto flutuante de precisão dupla, por exemplo: `0.0`, `-1.3``4e-7`.
- O tipo de `Bool` representa um valor booliano que pode ser `true` ou `false`.
- O tipo de `Qubit` representa um bit quântico ou qubit.
   `Qubit`s são opacas para o usuário; a única operação possível com eles, além de passá-los para outra operação, é testar a identidade (igualdade).
   Por fim, as ações em `Qubit`s são implementadas chamando instruções intrínsecas em um processador Quantum (ou em uma simulação delas).
- O tipo de `Pauli` representa um dos quatro operadores de Pauli de qubit único.
   Esse tipo é usado para indicar a operação base para rotações e para especificar o observável que está sendo medido.
   Este é um tipo enumerado que tem quatro valores possíveis: `PauliI`, `PauliX`, `PauliY`e `PauliZ`, que são constantes do tipo `Pauli`.
- O tipo de `Result` representa o resultado de uma medição.
   Este é um tipo enumerado com dois valores possíveis: `One` e `Zero`, que são constantes do tipo `Result`.
   `Zero` indica que a eigenvalue + 1 foi medida; `One` indica o-1 eigenvalue.
- O tipo de `Range` representa uma sequência de inteiros, denotada por `start..step..stop`, em que a indica que a etapa é opções. 
   `start .. stop` corresponde a `start..1..stop`e, por exemplo, `1..2..7` representa a sequência $\{1, 3, 5, 7\}$.
- O tipo de `String` é uma sequência de caracteres Unicode que é opaca para o usuário depois de criado.
  Esse tipo é usado para relatar mensagens a um host clássico no caso de um erro ou evento de diagnóstico.
- O tipo de `Unit` é o tipo que permite apenas um valor `()`. 
  Esse tipo é usado para indicar que a função ou operação Q # não retorna nenhuma informação. 

As constantes `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`e `Zero` são todos símbolos reservados em Q #.

## <a name="array-types"></a>Tipos de matriz

Dado um tipo válido de Q # `'T`, há um tipo que representa uma matriz de valores do tipo `'T`.
Esse tipo de matriz é representado como `'T[]`; por exemplo, `Qubit[]` ou `Int[][]`.
Por exemplo, uma coleção de inteiros é denotada `Int[]`, enquanto uma matriz de matrizes de `(Bool, Pauli)` valores é denotada `(Bool, Pauli)[][]`.

No segundo exemplo, observe que isso representa uma matriz potencialmente irregular de matrizes e não uma matriz bidimensional retangular.
O Q # não fornece suporte para matrizes multidimensionais retangulares.

Um valor de matriz pode ser escrito em código-fonte Q # usando colchetes em volta dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]`.
O tipo de um literal de matriz é determinado pelo tipo base comum de todos os itens na matriz. 

> [!WARNING]
> Os elementos de uma matriz não podem ser alterados após a criação da matriz.
> As instruções UPDATE-and-REASSIGN e/ou as expressões Copy-and-Update podem ser usadas para construir uma matriz modificada.

Como alternativa, uma matriz pode ser criada a partir de seu tamanho usando a palavra-chave `new`:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Em ambos os casos, após a construção de uma matriz, a função principal `Length` pode ser usada para obter o número de elementos como um `Int`.
As matrizes podem ser subscritos usando colchetes, com subscritos com o tipo `Int` ou tipo `Range`, para obter elementos únicos ou novas matrizes que contenham um subconjunto dos elementos de uma matriz.
Os subscritos das matrizes são baseados em zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipos de tupla

Dado zero ou mais tipos diferentes `T0`, `T1`,..., `Tn`, podemos denotar um novo *tipo de tupla* como `(T0, T1, ..., Tn)`.
Os tipos usados para construir um novo tipo de tupla podem ser tuplas, como em `(Int, (Qubit, Qubit))`.
No entanto, esse aninhamento é sempre finito, pois os tipos de tupla não podem, sob nenhuma circunstância, conter.

Os valores do novo tipo de tupla são tuplas formadas por sequências de valores de cada tipo na tupla.
Por exemplo, `(3, false)` é uma tupla cujo tipo é o tipo de tupla `(Int, Bool)`.
É possível criar matrizes de tuplas, tuplas de matrizes, tuplas de subtuplas, etc.

A partir de Q # 0,3, `Unit` é o nome do *tipo* da tupla vazia; `()` é usado para o *valor*de tupla vazio.

As instâncias de tupla são imutáveis.
O Q # não fornece um mecanismo para alterar o conteúdo de uma tupla depois de criada.

As tuplas são um conceito poderoso usado em toda a p # para coletar valores juntos em um único valor, facilitando sua passagem.
Em particular, usando a notação de tupla, podemos expressar que cada operação e que pode ser chamado leva exatamente uma entrada e retorna exatamente uma saída.

### <a name="singleton-tuple-equivalence"></a>Equivalência de tupla singleton

É possível criar uma tupla singleton (elemento único), `('T1)`, como `(5)` ou `([1,2,3])`.
No entanto, Q # trata uma tupla singleton como totalmente equivalente a um valor do tipo incluído.
Ou seja, não há nenhuma diferença entre `5` e `(5)`, ou entre `5` e `(((5)))`ou entre `(5, (6))` e `(5, 6)`.

Essa equivalência aplica-se a todas as finalidades, incluindo atribuições e expressões.
É tão válido gravar `(5)+3` quanto gravar `5+3`e as duas expressões serão avaliadas como `8`.
Em particular, isso significa que uma operação ou função cuja tupla de entrada ou tipo de tupla de saída tem um campo pode ser considerada como um único argumento ou retornando um único valor.

Nós nos referimos a essa propriedade como _equivalência de tupla singleton_.

## <a name="user-defined-types"></a>Tipos definidos pelo usuário

Um arquivo Q # pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.
Para qualquer tipo de tupla `T`, podemos declarar um novo tipo definido pelo usuário que seja um subtipo de `T` com a instrução `newtype`.
No namespace @"microsoft.quantum.canon", por exemplo, números complexos são definidos como um tipo definido pelo usuário:

```qsharp
newtype Complex = (Double, Double);
```

Essa instrução cria um novo tipo com dois itens anônimos do tipo `Double`.   
Além de itens anônimos, os tipos definidos pelo usuário também dão suporte a itens nomeados a partir do Q # versão 0,7 ou superior. Por exemplo, poderíamos ter nomeado o to Items `Re` para o Double representando a parte real de um número complexo e `Im` para a parte imaginária: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Nomear um item em um tipo definido pelo usuário não significa que todos os itens precisam ser nomeados-qualquer combinação de itens nomeados e sem nome é suportada. Além disso, os itens internos também podem ser nomeados.
O tipo `Nested` conforme definido abaixo, por exemplo, tem um tipo subjacente `(Double, (Int, String))`, do qual apenas o item do tipo `Int` é nomeado e todos os outros itens são anônimos. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
Os itens nomeados têm a vantagem de que eles podem ser acessados diretamente por meio do operador de acesso `::`. 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Para acessar itens anônimos por outro lado, o valor encapsulado primeiro precisa ser extraído usando o operador de sufixo `!`.
O operador "Unwrap", `!`, permite extrair o valor contido em um tipo definido pelo usuário.
O tipo dessa expressão de "desencapsulamento" é o tipo subjacente do tipo definido pelo usuário. 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

O operador de desencapsulamento não encapsula exatamente uma camada de encapsulamento.
Vários operadores de desencapsulamento podem ser usados para acessar um valor com disposição multiplicada.

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

Dê uma olhada na seção sobre [desencapsulamento de expressões](xref:microsoft.quantum.language.expressions#unwrap-expressions) e [precedência de operadores](xref:microsoft.quantum.language.expressions#operator-precedence) para obter mais detalhes.

Os valores de um tipo definido pelo usuário podem ser criados chamando o construtor de tipo correspondente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Como alternativa, novos valores podem ser criados de existentes usando [expressões de copiar e atualizar](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). Assim como para matrizes, essas expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados. Para esses valores são definidos como aqueles definidos no lado direito da expressão. Qualquer outra construção de linguagem, como por exemplo, [atualizar e reatribuir instruções](xref:microsoft.quantum.language.statements#update-and-reassign-statement), que estão disponíveis para itens de matriz existem para itens nomeados em tipos definidos pelo usuário também.

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

Tipos definidos pelo usuário podem ser usados em qualquer lugar que qualquer outro tipo possa ser usado.
Em particular, é possível definir uma matriz de um tipo definido pelo usuário e incluir um tipo definido pelo usuário como um elemento de um tipo de tupla.

Não é possível criar estruturas de tipo recursiva.
Ou seja, o tipo que define um tipo definido pelo usuário pode não ser um tipo de tupla que inclua um elemento do tipo definido pelo usuário.
Em geral, os tipos definidos pelo usuário podem não ter dependências cíclicas entre si, portanto, o seguinte conjunto de definições de tipo seria ilegal:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

Além de fornecer aliases curtos para tipos de tupla potencialmente complicadas, uma vantagem significativa de definir esses tipos é que eles podem documentar a intenção de um valor específico.
Retornando ao exemplo de `Complex`, um também poderia ter definido as coordenadas polares 2D como um tipo definido pelo usuário:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Embora tanto `Complex` quanto `Polar` tenham um tipo subjacente `(Double, Double)`, os dois tipos são totalmente incompatíveis em Q #, minimizando o risco de chamar acidentalmente uma função matemática complexa com coordenadas polares e vice-versa.
Dessa forma, os tipos definidos pelo usuário têm uma função semelhante à de registros F# , por exemplo. 


## <a name="operation-and-function-types"></a>Operação e tipos de função

Uma _operação_ Q # é uma sub-rotina Quantum.
Ou seja, é uma rotina que possa ser chamada que contém operações Quantum.

Uma _função_ Q # é uma sub-rotina clássica usada em um algoritmo Quantum.
Ele pode conter código clássico, mas não há operações de Quantum.
Especificamente, as funções podem não alocar ou emprestar qubits, nem podem chamar operações.
No entanto, é possível passá-los de operações ou qubits para processamento.
As funções são, portanto, totalmente determinísticas no sentido de que chamá-las com os mesmos argumentos sempre produzirá o mesmo resultado. 

Juntas, as operações e funções são chamadas de _callables_.  Você pode ver alguns [exemplos](#examples) deles abaixo.

Todos os chamadores de Q # são considerados para pegar um único valor como entrada e retornar um único valor como saída.
Os valores de entrada e saída podem ser tuplas.
Chamadores que não têm `Unit`de retorno de resultado.
Os chamadores que não têm nenhuma entrada usam a tupla vazia como entrada.

O tipo básico para qualquer callable é escrito como `('Tinput => 'Tresult)` ou `('Tinput -> 'Tresult)`, onde `'Tinput` e `'Tresult` são tipos.
O primeiro formulário, com `=>`, é usado para operações; o segundo formulário, com `->`, para funções.
Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura de uma possível operação de medição de qubit único.

Os tipos de função são completamente especificados por sua assinatura.
Por exemplo, uma função que computa o seno de um ângulo teria o tipo `(Double -> Double)`.

Operações — mas não funções — têm determinadas _características_ adicionais que são expressas como parte do tipo de operação. Essas características incluem informações sobre o que transmissão functors a operação dá suporte.
Transmissão functors são metaoperações que geram uma especialização de uma operação de base; consulte [transmissão functors](#functors), abaixo.

Os tipos de operação são especificados pelo tipo de entrada, tipo de saída e suas características.    
Para exigir suporte para o `Controlled` e/ou `Adjoint` functor em um tipo de operação, precisamos adicionar uma anotação que indica as características correspondentes.
Um `is Ctl` de anotação, por exemplo, indica que a operação é controlável. Se quisermos exigir que uma operação desse tipo dê suporte a `Adjoint` e `Controlled` functor, poderemos expressar isso como `(Qubit => Unit is Adj + Ctl)`. As características de operação usadas `Adj` e `Ctl` estritamente falando são dois conjuntos predefinidos de rótulos, onde cada rótulo indica as características de uma operação específica como, por exemplo, o suporte para um determinado functor.
Portanto, `+` é usado para indicar a União desses dois conjuntos, e `*` é usado para indicar a interseção, ou seja, os rótulos que são comuns a ambos os conjuntos.  

Por exemplo, a operação de `X` Pauli tem o tipo `(Qubit => Unit is Adj + Ctl)`.
Um tipo de operação que não dá suporte a nenhum transmissão functors é especificado por seu tipo de entrada e saída sozinho, sem anotação adicional.


### <a name="type-parameterized-functions-and-operations"></a>Funções e operações com parâmetros de tipo

Tipos chamáveis podem conter parâmetros de tipo.
Os parâmetros de tipo são indicados por um símbolo prefixado por uma aspa simples; por exemplo, `'A` é um parâmetro de tipo legal.

Um parâmetro de tipo pode aparecer mais de uma vez em uma única assinatura.
Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e retorna os resultados coletados teriam a assinatura `(('A[], 'A->'A) -> 'A[])`.
Da mesma forma, uma função que retorna a composição de duas operações pode ter `((('A=>'B), ('B=>'C)) -> ('A=>'C))`de assinatura.

Ao invocar um callable-parametrizado de tipo, todos os argumentos que têm o mesmo parâmetro de tipo devem ser do mesmo tipo.

O Q # não fornece um mecanismo para restringir os possíveis tipos que podem ser substituídos por um parâmetro de tipo.

### <a name="type-compatibility"></a>Compatibilidade de tipo

Uma operação com suporte adicional a transmissão functors pode ser usada em qualquer lugar de uma operação com menos transmissão functors, mas a mesma assinatura é esperada.
Por exemplo, uma operação do tipo `(Qubit => Unit is Adj)` pode ser usada em qualquer lugar que uma operação do tipo `(Qubit => Unit)` seja esperada.

Q # é covariant com relação a tipos de retorno que podem ser chamados: um callable que retorna um tipo `'A` é compatível com um callable com o mesmo tipo de entrada e um tipo de resultado ao qual `'A` é compatível.

Q # é contravariant em relação aos tipos de entrada: um callable que usa um tipo `'A` como entrada é compatível com um callable com o mesmo tipo de resultado e um tipo de entrada compatível com `'A`.

Ou seja, dadas as seguintes definições:

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

o seguinte é verdadeiro:

- A operação `ConjugateInvertibleWith` pode ser invocada com um argumento `inner` de `Invertible` ou `Unitary`.
- A operação `ConjugateUnitaryWith` pode ser invocada com um argumento `inner` de `Unitary`, mas não `Invertible`.
- Um valor do tipo `(Qubit[] => Unit is Adj + Ctl)` pode ser retornado de `ConjugateInvertibleWith`.

> [!IMPORTANT]
> A p # 0,3 apresenta uma diferença significativa no comportamento de tipos definidos pelo usuário.

Os tipos definidos pelo usuário são tratados como uma versão encapsulada do tipo subjacente, em vez de como um subtipo.
Isso significa que um valor de um tipo definido pelo usuário não é utilizável, em que um valor do tipo subjacente é esperado.

### <a name="functors"></a>Transmissão functors

Um functor em Q # é um alocador que define uma nova operação de outra operação.
Transmissão functors têm acesso à implementação da operação base ao definir a implementação da nova operação.
Portanto, o transmissão functors pode executar funções mais complexas do que as funções tradicionais de nível superior.

Transmissão functors não tem uma representação no sistema do tipo Q #. Portanto, no momento, não é possível associá-los a uma variável ou passá-los como argumentos. 

Um functor é usado aplicando-o a uma operação, retornando uma nova operação.
Por exemplo, a operação resultante da aplicação do `Adjoint` functor à operação `Y` é gravada como `Adjoint Y`.
A nova operação pode ser invocada como qualquer outra operação.
Assim, `Adjoint Y(q1)` aplica o functor de modo adjacente à operação `Y` para gerar uma nova operação e aplica essa nova operação a `q1`.

Da mesma forma, `Controlled X(controls, target)` aplica o functor controlado à operação de `X` para gerar uma nova operação e aplica essa nova operação a `controls` e `target`.

Os dois transmissão functors padrão em Q # são `Adjoint` e `Controlled`.

#### <a name="adjoint"></a>Adjacente

Na computação Quantum, o adjoin de uma operação é a transpoção de conjugada complexa da operação.
Para operações que implementam um operador unitário, o adjacente é o inverso da operação.
Para uma operação simples que simplesmente invoca uma sequência de outras operações de unitário em um conjunto de qubits, o erro pode ser computado aplicando o adjoints das suboperações no mesmo qubits, na sequência inversa.

Dada uma expressão de operação, uma nova expressão de operação pode ser formada usando o `Adjoint` functor.
Por exemplo, `Adjoint QFT` designa o adjoin da operação `QFT`.
A nova operação tem a mesma assinatura e tipo que a operação base.
Em particular, a nova operação também permite `Adjoint`e permitirá `Controlled` se e somente se a operação base tiver feito isso.

O functor de adjacente é seu próprio inverso; ou seja, `Adjoint Adjoint Op` é sempre o mesmo que `Op`.

#### <a name="controlled"></a>Controlado

A versão controlada de uma operação é uma nova operação que aplica efetivamente a operação base somente se todas as qubits de controle estiverem em um estado especificado.
Se o controle qubits estiver em superposição, a operação base será aplicada coerentemente à parte apropriada da superposição.
Portanto, as operações controladas geralmente são usadas para gerar Entanglement.

Em Q #, as versões controladas sempre pegam uma matriz de qubits de controle e o estado especificado é sempre para todas as qubits de controle no estado computacional (`PauliZ`) `One`, $ \ket{1}$.
O controle com base em outros Estados pode ser obtido aplicando a operação unitário apropriada ao qubits de controle antes da operação controlada e, em seguida, aplicando os inversos da operação unitário após a operação controlada.
Por exemplo, a aplicação de uma operação de `X` a um qubit de controle antes e depois de uma operação controlada fará com que a operação controle o estado de `Zero` ($ \ket{0}$) para esse qubit; a aplicação de uma operação de `H` antes e depois controlará o estado de `One` de `PauliX`, que é-1 eigenvalue de Pauli X, $ \ket{-} \mathrel{: =} (\ket{0}-\ket{1})/\sqrt{2}$ em vez do estado `PauliZ` `One`.

Dada uma expressão de operação, uma nova expressão de operação pode ser formada usando o `Controlled` functor.
A assinatura da nova operação é baseada na assinatura da operação original.
O tipo de resultado é o mesmo, mas o tipo de entrada é de duas tuplas com uma matriz qubit que mantém o controle qubit (s) como o primeiro elemento e os argumentos da operação original como o segundo elemento.
A nova operação dá suporte a `Controlled`e dará suporte a `Adjoint` se e somente se a operação original tiver feito isso.

Se a operação original levou apenas um único argumento, a equivalência de tupla singleton entrará em ação aqui.
Por exemplo, `Controlled X` é a versão controlada da operação de `X`.
`X` tem `(Qubit => Unit is Adj + Ctl)`de tipo, portanto `Controlled X` tem o tipo `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; devido à equivalência de tupla singleton, isso é o mesmo que `((Qubit[], Qubit) => Unit is Adj + Ctl)`.

Se a operação base levou vários argumentos, lembre-se de colocar os argumentos correspondentes da versão controlada da operação entre parênteses para convertê-los em uma tupla.
Por exemplo, `Controlled Rz` é a versão controlada da operação de `Rz`.
`Rz` tem `((Double, Qubit) => Unit is Adj + Ctl)`de tipo, portanto `Controlled Rz` tem o tipo `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.
Portanto, `Controlled Rz(controls, (0.1, target))` seria uma invocação válida de `Controlled Rz` (Observe os parênteses ao `0.1, target`).

Como outro exemplo, `CNOT(control, target)` pode ser implementado como `Controlled X([control], target)`. Se um destino deve ser controlado por dois qubits de controle (CCNOT), podemos usar `Controlled X([control1, control2], target)` instrução.

### <a name="examples"></a>Exemplos

Este exemplo de uma operação Q # é proveniente do exemplo de [medida](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) . Em operações, podemos alocar qubits e usar operações Quantum nesses qubits, como `H` e `X`:

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
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

Este exemplo de uma função é proveniente do exemplo de [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) . Ele contém código puramente clássico. Você pode ver que, ao contrário do exemplo acima, nenhum qubits está alocado e nenhuma operação de Quantum é usada.


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

Também é possível que uma função seja passada qubits para processamento, como neste exemplo do exemplo de [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) . Qubits são passados para a função e usados para processamento, embora em nenhum momento os próprios Estados de qubit sejam modificados.

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

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
