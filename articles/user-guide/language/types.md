---
title: 'Tipos em Q #'
description: Conheça os diferentes tipos utilizados na linguagem de programação Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431143"
---
# <a name="types-in-q"></a>Tipos em Q #

Esta página descreve o modelo do tipo Q# e descreve a sintaxe para especificar e trabalhar com tipos.
A página seguinte, [Type Expressions,](xref:microsoft.quantum.guide.expressions)detalha como criar e operar em expressões deste tipo.

Notamos que q# é uma linguagem *fortemente dactilografada,* de tal forma que uma utilização cuidadosa destes tipos pode ajudar o compilador a fornecer fortes garantias sobre os programas Q# no momento da compilação.
A fim de fornecer as garantias mais fortes possíveis, as conversões entre tipos em Q# devem ser explícitas utilizando chamadas para funções que expressem essa conversão. Uma variedade dessas funções são fornecidas como parte do espaço de <xref:microsoft.quantum.convert> nome.
As upcasts para tipos compatíveis, por outro lado, acontecem implicitamente. 

Q# fornece ambos os tipos primitivos, que podem ser usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.
Descrevemos cada um no resto desta secção.

## <a name="primitive-types"></a>Tipos Primitivos

A língua Q# fornece vários *tipos primitivos,* a partir dos quais outros tipos podem ser construídos:

- O tipo representa um inteiro assinado de `Int` 64 bits, por exemplo: `2` `107` . `-5`
- O `BigInt` tipo representa um inteiro assinado de tamanho arbitrário, por `2L` exemplo, `107L` `-5L` .
   Este tipo baseia-se no .NET<xref:System.Numerics.BigInteger>
   tipo.
- O `Double` tipo representa um número de ponto flutuante de dupla precisão, por exemplo: `0.0` . . `-1.3` `4e-7` .
- O `Bool` tipo representa um valor Boolean o que pode ser ou `true` `false` .
- O `Range` tipo representa uma sequência de inteiros, denotadopor, onde `start..step..stop` denotar o passo são opções. 
   Isto `start .. stop` corresponde `start..1..stop` a, e por exemplo, `1..2..7` representa a sequência $ \{ 1, 3, 5, 7 \} $.
- O `String` tipo é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.
  Este tipo é usado para relatar mensagens a um hospedeiro clássico em caso de erro ou evento de diagnóstico.
- O `Unit` tipo é do tipo que permite apenas um valor `()` . 
  Este tipo é utilizado para indicar que a função ou operação Q# não devolve nenhuma informação. 
- O `Qubit` tipo representa um bit quântico ou qubit.
   `Qubit`s são opacos para o utilizador; a única operação possível com eles, para além de os passar para outra operação, é testar a identidade (igualdade).
   Em última análise, as ações em `Qubit` s são implementadas chamando instruções intrínsecas num processador quântico (ou uma simulação do mesmo).
- O `Pauli` tipo representa um dos quatro operadores de Moqubit Pauli.
   Este tipo é utilizado para denotar o funcionamento da base para rotações e para especificar o observável que está a ser medido.
   Este é um tipo enumerado que tem quatro valores possíveis: `PauliI` , , e , que são `PauliX` `PauliY` `PauliZ` constantes de `Pauli` tipo.
- O `Result` tipo representa o resultado de uma medição.
   Este é um tipo enumerado com dois valores possíveis: `One` `Zero` e, que são constantes de `Result` tipo.
   `Zero`indica que o valor +1 foi medido; `One`indica o -1 eigenvalue.

As `true` constantes, , , , , , e são `false` todos `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` símbolos reservados em Q#.

## <a name="array-types"></a>Tipos de matriz

Dado qualquer tipo Q# `'T` válido, existe um tipo que representa uma variedade de valores de tipo `'T` .
Este tipo de matriz é representado `'T[]` como; por exemplo, `Qubit[]` ou `Int[][]` .
Por exemplo, uma coleção de inteiros é denotada, `Int[]` enquanto uma série de conjuntos de `(Bool, Pauli)` valores é denotado `(Bool, Pauli)[][]` .

No segundo exemplo, note que isto representa uma matriz potencialmente irregular de matrizes, e não uma matriz bidimensional retangular.
Q# não fornece suporte para matrizes multidimensionais retangulares.

Um valor de matriz pode ser escrito no código fonte Q# utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]` .
O tipo de matriz literal é determinado pelo tipo de base comum de todos os itens da matriz. 

> [!WARNING]
> Os elementos de uma matriz não podem ser alterados após a criação da matriz.
> [As declarações de atualização e reatribuição](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) e/ou [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) podem ser utilizadas para construir uma matriz modificada.

Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a `new` palavra-chave:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Em qualquer dos casos, uma vez construída uma matriz, a função central `Length` pode ser utilizada para obter o número de elementos como `Int` .
As matrizes podem ser subscritas utilizando suportes quadrados, com subscripts que tenham tipo `Int` ou `Range` tipo, para obter elementos únicos ou novas matrizes contendo um subconjunto dos elementos de uma matriz.
Os subscripts de matrizes são baseados em zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipos de tuple

Tendo em conta tipos zero ou mais `T0` `T1` diferentes, `Tn` podemos denotar um novo tipo de *tuple* como `(T0, T1, ..., Tn)` .
Os tipos usados para construir um novo tipo de tuple podem ser tuples, como em `(Int, (Qubit, Qubit))` .
No entanto, esta nidificação é sempre finita, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.

Os valores do novo tipo de tuple são tuples formados por sequências de valores de cada tipo na tuple.
Por exemplo, `(3, false)` é uma tuple cujo tipo é do tipo tuple `(Int, Bool)` .
É possível criar conjuntos de tuples, tuples de matrizes, tuples de sub-tuples, etc.

A partir do Q# 0.3, `Unit` é o nome do *tipo* de tuple vazio; é usado para `()` o *valor*de tuple vazio .

Os casos de tuple são imutáveis.
Q# não fornece um mecanismo para alterar o conteúdo de uma tuple uma vez criado.

Tuples são um conceito poderoso usado ao longo de Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.
Em particular, usando a notação de tuple, podemos expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.

### <a name="singleton-tuple-equivalence"></a>Equivalência singleton Tuple

É possível criar uma tuple singleton (elemento único), `('T1)` como `(5)` ou `([1,2,3])` .
No entanto, Q# trata uma túnica singleton como completamente equivalente a um valor do tipo fechado.
Ou seja, não há diferença entre `5` `(5)` e, ou entre `5` `(((5)))` e, ou entre `(5, (6))` e `(5, 6)` .
É tão válido escrever `(5)+3` como `5+3` escrever, e ambas as expressões avaliarão para `8` .

Esta equivalência aplica-se a todos os fins, incluindo atribuição e expressões.
Dada qualquer expressão, essa mesma expressão em parênteses é uma expressão do mesmo tipo.
Por exemplo, `(7)` é uma `Int` expressão, é uma expressão de tipo `([1,2,3])` de matriz de `Int` s, e é uma expressão com tipo `((1,2))` `(Int, Int)` .

Isto significa, em particular, que uma operação ou função cujo tipo de tuple de entrada ou tuple de saída tem um campo pode ser considerado como tendo um único argumento ou devolvendo um único valor.

Referimo-nos a esta propriedade como _equivalência de tuple singleton._


## <a name="user-defined-types"></a>Tipos definidos pelo utilizador

Uma declaração de tipo definido pelo utilizador consiste na palavra-chave, seguida do nome do tipo definido pelo `newtype` utilizador, uma `=` especificação de tipo válido e um ponto evíomina terminando.

Por exemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```

Cada ficheiro de origem Q# pode declarar qualquer número de tipos definidos pelo utilizador.
Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de funcionamento e função.

Os tipos definidos pelo utilizador são distintos mesmo que os tipos de base sejam idênticos.
Em particular, não existe uma conversão automática entre valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.

### <a name="named-vs-anonymous-items"></a>Nomeado vs. itens anónimos

Um ficheiro Q# pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.
Para qualquer tipo de `T` tuple, podemos declarar um novo tipo definido pelo utilizador que é um subtipo de `T` com a `newtype` declaração.
No @"microsoft.quantum.math" espaço de nome, por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:

```qsharp
newtype Complex = (Double, Double);
```
Esta afirmação cria um novo tipo com dois itens anónimos de tipo `Double` .   

Além de itens anónimos, os tipos definidos pelo utilizador também suportam *itens nomeados* a partir da versão Q# 0.7 ou superior. Por exemplo, poderíamos ter nomeado os itens `Re` para o duplo representando a parte real de um número complexo e para a parte `Im` imaginária: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportado. Além disso, os itens internos também podem ser nomeados.
O tipo `Nested` definido abaixo, por exemplo, tem um tipo `(Double, (Int, String))` subjacente, do qual apenas o item do tipo `Int` é nomeado e todos os outros itens são anónimos. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Os itens nomeados têm a vantagem de poderem ser acedidos diretamente através do *operador* de `::` acesso. 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Além de fornecer pseudónimos curtos para tipos de tuple potencialmente complicados, uma vantagem significativa de definir tais tipos é que eles podem documentar a intenção de um valor particular.
Voltando ao exemplo `Complex` de, poderia também ter definido coordenadas polares 2D como um tipo definido pelo utilizador:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Apesar de ambos `Complex` e ambos terem um tipo `Polar` `(Double, Double)` subjacente, os dois tipos são totalmente incompatíveis em Q#, minimizando o risco de chamar acidentalmente uma função matemática complexa com coordenadas polares e vice-versa.
Desta forma, os tipos definidos pelo utilizador têm um papel semelhante ao dos Registos em F# por exemplo. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Aceda a itens anónimos com o operador de desembrulhar

Para aceder a itens anónimos, por outro lado, o valor embrulhado primeiro precisa de ser extraído através do operador de postfix `!` .
O operador "desembrulhar", `!` permite extrair o valor contido num tipo definido pelo utilizador.
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

Mais detalhes sobre o operador de desembrulhar podem ser encontrados em [Expressões tipo em Q#](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Criação de valores de tipos definidos pelo utilizador

Os valores de um tipo definido pelo utilizador podem ser criados chamando o construtor de tipo correspondente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternativamente, novos valores podem ser criados a partir dos existentes usando [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Tal como para as matrizes, tais expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados. Para estes, os valores são definidos para os definidos no lado direito da expressão. Quaisquer outras construções linguísticas, como, por exemplo, [declarações de atualização e reatribuição,](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)que estejam disponíveis para itens de matriz, existem também para itens nomeados em tipos definidos pelo utilizador.

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

Nota não é possível criar estruturas de tipo recursivos.
Ou seja, o tipo que define um tipo definido pelo utilizador pode não ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.
De um modo mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas entre si, pelo que o seguinte conjunto de definições de tipo seria ilegal:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Tipos de Funcionamento e Função

O tipo básico para qualquer callable é escrito como `('Tinput => 'Tresult)` ou , onde ambos e tipos `('Tinput -> 'Tresult)` `'Tinput` `'Tresult` são.
Estes são chamados a *assinatura* do callable.

Todos os callables Q# são considerados como tendo um único valor como entrada e devolver um único valor como saída.
Tanto os valores de entrada como de saída podem ser tuples.
Callables que não têm retorno de `Unit` resultados.
Os inputáveis que não têm entrada tomam a túnica vazia como entrada.

> [!NOTE]
> A primeira forma, `=>` com, é utilizada para operações; a segunda forma, `->` com, para funções.
> Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura para uma possível operação de medição de qubit único.
Os tipos de *funções* são completamente especificados pela sua assinatura.
Por exemplo, uma função que computa o seno de um ângulo teria tipo `(Double -> Double)` .

*Operações*---mas não funções---têm certas características adicionais que são expressas como parte do tipo de operação. Estas características incluem informações sobre os *functores* que a operação suporta.
Por exemplo, se a execução da operação puder ser condicionada ao estado de outros qubits, deve apoiar o `Controlled` functor; se a operação tiver um inverso, deverá apoiar o `Adjoint` functor. Os functores e as operações são discutidos detalhadamente nas [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions), mas aqui simplesmente discutimos como isso altera a assinatura da operação.

Para exigir apoio ao `Controlled` functor e/ou `Adjoint` functor num tipo de operação, precisamos adicionar uma anotação indicando as características correspondentes.
Uma anotação `is Ctl` (por `(Qubit => Unit is Ctl)` exemplo) indica que a operação é controlável--- ou seja, é a execução condicionada no estado de outro qubit ou qubits. Da mesma forma, `is Adj` indica que a operação tem um adjoint; ou simplesmente, pode ser "invertida" de modo a que sucessivamente aplique uma operação e, em seguida, o seu adjoint a um Estado deixe o Estado inalterado. 

Se quisermos exigir que uma operação desse tipo suporte tanto o `Adjoint` functor como o `Controlled` functor podemos expressar isto como `(Qubit => Unit is Adj + Ctl)` . Por exemplo, a operação Pauli incorporada <xref:microsoft.quantum.intrinsic.x> tem tipo `(Qubit => Unit is Adj + Ctl)` . 

Um tipo de funcionamento que não suporta functores é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.

### <a name="type-parameterized-functions-and-operations"></a>Funções e operações parametrizadas tipo

Os tipos de callable podem conter parâmetros de tipo.
Os parâmetros do tipo são indicados por um símbolo prefixado por uma única citação; por exemplo, `'A` é um parâmetro de tipo legal.
Os detalhes sobre a definição de callables parâmetros tipo são fornecidos na página [Operações e Funções na](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) página Q# .

Um parâmetro de tipo pode aparecer mais de uma vez numa única assinatura.
Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e devolve os resultados recolhidos teria assinatura `(('A[], 'A->'A) -> 'A[])` .
Da mesma forma, uma função que retorne a composição de duas operações pode ter assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Ao invocar um tipo de escala tometável, todos os argumentos que tenham o mesmo parâmetro devem ser do mesmo tipo.

Q# não fornece um mecanismo para limitar os tipos possíveis que podem ser substituídos por um parâmetro de tipo.

## <a name="whats-next"></a>O que se segue?
Agora que já viu todos os tipos que compõem a língua Q#, pode dirigir-se a [Type Expressions em Q#](xref:microsoft.quantum.guide.expressions) para ver como criar e manipular expressões destes vários tipos.


