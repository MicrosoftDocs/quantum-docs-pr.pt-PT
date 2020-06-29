---
title: Tipos em Q#
description: Saiba mais sobre os diferentes tipos utilizados na linguagem de programação Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: e37ce6e3a2dfad5395cdecf06178d64ec51b79f1
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415291"
---
# <a name="types-in-q"></a>Tipos em Q#

Este artigo descreve o modelo do tipo Q# e a sintaxe para especificar e trabalhar com tipos. Para obter detalhes sobre como criar e operar em expressões deste tipo, consulte [Expressões tipo](xref:microsoft.quantum.guide.expressions).

Notamos que Q# é uma linguagem *fortemente dactilografada,* de modo que o uso cuidadoso destes tipos pode ajudar o compilador a fornecer garantias fortes sobre os programas Q# no momento da compilação.
Para fornecer as garantias mais fortes possíveis, as conversões entre os tipos em Q# devem ser explícitas usando chamadas para funções que expressem essa conversão. Q# fornece uma variedade de tais funções como parte do espaço de <xref:microsoft.quantum.convert> nome.
As upcasts para tipos compatíveis, por outro lado, acontecem implicitamente. 

Q# fornece ambos os tipos primitivos, que são usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.
Descrevemos cada um no resto deste artigo.

## <a name="primitive-types"></a>Tipos Primitivos

O idioma Q# fornece os seguintes *tipos primitivos,* todos os quais pode utilizar diretamente nos programas Q#. Também pode usar estes tipos primitivos para construir novos tipos.

- O `Int` tipo representa um número inteiro assinado de 64 bits, por exemplo, `2` . . . `107` `-5` .
- O `BigInt` tipo representa um número inteiro assinado de tamanho arbitrário, por `2L` `107L` exemplo, , . `-5L` .
   Este tipo baseia-se no .NET<xref:System.Numerics.BigInteger>
   tipo.

- O `Double` tipo representa um número de ponto flutuante de dupla precisão, por `0.0` exemplo, , . . `-1.3` `4e-7` .
- O `Bool` tipo representa um valor booleano de qualquer um ou `true` `false` .
- O `Range` tipo representa uma sequência de inteiros, denotada `start..step..stop` por, onde denotar o passo é opcional. 
   Por exemplo, `start .. stop` corresponde a , e representa a sequência $ `start..1..stop` `1..2..7` \{ 1, 3, 5, 7 \} $.
- O `String` tipo é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.
  Utilize o `string` tipo para reportar mensagens a um anfitrião clássico em caso de erro ou evento de diagnóstico.
- O `Unit` tipo pode ter apenas um valor, `()` . 
  Utilize este tipo para indicar que uma função Q# ou operação não retorna nenhuma informação. 
- O `Qubit` tipo representa um bit quântico ou qubit.
   `Qubit`s são opacos para o utilizador. A única operação possível com eles, para além de passá-los para outra operação, é testar a identidade (igualdade).
   Em última análise, implementa ações em `Qubit` s, chamando instruções intrínsecas num processador quântico (ou um simulador quântico).
- O `Pauli` tipo representa um dos quatro operadores pauli de um único qubit.
   Utilize este tipo para denotar o funcionamento da base para rotações e especificar o que está a ser medido.
   É um tipo enumerado que tem quatro valores possíveis: `PauliI` `PauliX` , , `PauliY` `PauliZ` e, que são constantes de tipo `Pauli` .
- O `Result` tipo representa o resultado de uma medição.
   É um tipo enumerado com dois valores possíveis: `One` `Zero` e, que são constantes do tipo `Result` .
   `Zero`indica que o valor de +1 eigen foi medido; `One`indica que o -1 eigenvalue foi medido.

As constantes `true` , , , , , , , e são `false` todos `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` símbolos reservados em Q#.

## <a name="array-types"></a>Tipos de Matrizes

* Para qualquer tipo Q# válido, existe um tipo que representa uma matriz de valores desse tipo.
    Por exemplo, `Qubit[]` e `(Bool, Pauli)[]` representam matrizes de `Qubit` valores e `(Bool, Pauli)` valores de tuple.

* Uma variedade de matrizes também é válida. Expandindo-se no exemplo anterior, uma série de `(Bool, Pauli)` matrizes é denotada `(Bool, Pauli)[][]` .

> [!NOTE] 
> Este `(Bool, Pauli)[][]` exemplo, representa uma matriz potencialmente irregular de matrizes e não uma matriz bidimensional retangular. Q# não suporta matrizes multidimensionais retangulares.

* Um valor de matriz pode ser escrito no código fonte Q# utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]` .
O tipo de base comum de todos os itens da matriz determina o tipo de matriz literal. Assim, construir uma matriz com elementos que não têm um tipo de base comum levanta um erro.  
Por exemplo, consulte [conjuntos de chamadas.](xref:microsoft.quantum.guide.expressions#arrays-of-callables)

    > [!WARNING]
    > Uma vez criados, os elementos de uma matriz não podem ser alterados.
    > Para construir uma matriz modificada, utilize [declarações de atualização e reatribuição](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) ou [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).

* Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a `new` palavra-chave:

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* Utilize a função central `Length` para obter o número de elementos de uma matriz como `Int` .
* As matrizes podem ser subscritadas para obter elementos únicos ou novas matrizes que contenham um subconjunto dos elementos de uma matriz.
Os subscritos de matrizes são de base zero e devem ser tipo `Int` ou `Range` tipo:

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>Tipos tuple

Tuples é um conceito poderoso usado ao longo de Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.
Em particular, usando a notação de tuple, você pode expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.

* Dado zero ou mais tipos `T0` `T1` diferentes, ...pode `Tn` denotar um novo *tipo de tuple* como `(T0, T1, ..., Tn)` .
Os tipos usados para construir um novo tipo de tuple podem ser tuples, como em `(Int, (Qubit, Qubit))` .
No entanto, esse nidificação é sempre finito, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.

* Os valores do novo tipo tuple são tuples formados por sequências de valores de cada tipo no tuple.
Por exemplo, `(3, false)` é um tuple cujo tipo é o tipo tuple `(Int, Bool)` .
É possível criar matrizes de tuples, tuples de matrizes, tuples de sub-tuples, e assim por diante.

* A partir de Q# 0.3, `Unit` é o nome do *tipo* de tuple vazio; é usado para `()` o *valor* do tuple vazio.

* As instâncias de tuple são imutáveis.
Q# não fornece um mecanismo para alterar o conteúdo de um tuple uma vez criado.



### <a name="singleton-tuple-equivalence"></a>Equivalência de Tuple Singleton

É possível criar uma tuple singleton (single-element), `('T1)` como `(5)` ou `([1,2,3])` .
No entanto, Q# trata um tuple singleton como equivalente a um valor do tipo fechado.
Ou seja, não há diferença entre `5` `(5)` e, ou entre `5` `(((5)))` e, ou entre `(5, (6))` e `(5, 6)` .
É tão válido escrever `(5)+3` como `5+3` escrever; ambas as expressões `8` avaliam.

Esta equivalência aplica-se para todos os efeitos, incluindo atribuição e expressões.
Dada qualquer expressão, a mesma expressão em anexo em parênteses é uma expressão do mesmo tipo.
Por exemplo, `(7)` é uma expressão do `Int` tipo, é uma expressão do `([1,2,3])` `Int[]` tipo, e é uma expressão do `((1,2))` `(Int, Int)` tipo.

Isto significa, em particular, que pode ver uma operação ou função cujo tipo de tuple ou de saída tem um campo como tendo um único argumento ou devolvendo um único valor.

Referimo-nos a esta propriedade como _equivalência de tuple singleton._


## <a name="user-defined-types"></a>Tipos definidos pelo utilizador

Uma declaração de tipo definido pelo utilizador consiste na `newtype` palavra-chave, seguida do nome do tipo definido pelo utilizador, `=` uma especificação de tipo válido e um ponto de terminação.

Por exemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* Cada ficheiro de origem Q# pode declarar qualquer número de tipos definidos pelo utilizador.
* Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento e os nomes das funções.
* Os tipos definidos pelo utilizador são distintos, mesmo que os tipos de base sejam idênticos.
Em particular, não existe uma conversão automática entre os valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.

### <a name="named-vs-anonymous-items"></a>Nomeados vs. itens anónimos

Um ficheiro Q# pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.
Para qualquer tipo de `T` tuple, pode declarar um novo tipo definido pelo utilizador que é um subtipo `T` de com a `newtype` declaração.
No @"microsoft.quantum.math" espaço de nomes, por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:

```qsharp
newtype Complex = (Double, Double);
```
Esta afirmação cria um novo tipo com dois itens anónimos do tipo `Double` .   

Além de itens anónimos, os tipos definidos pelo utilizador também *suportam itens nomeados* a partir da versão Q# 0.7 ou superior. Por exemplo, pode nomear os itens `Re` para o duplo representando a parte real de um número complexo e para a parte `Im` imaginária: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportada. Além disso, os itens internos também podem ser nomeados.
O tipo `Nested` , tal como definido abaixo, por exemplo, tem um tipo `(Double, (Int, String))` subjacente, do qual apenas o item do tipo `Int` é nomeado, e todos os outros itens são anónimos. 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

Os itens nomeados têm a vantagem de poderem ser acedidos diretamente através do *operador de acesso.* `::` 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

Além de fornecer pseudónimos curtos para tipos de tuple potencialmente complicados, uma vantagem significativa de definir tais tipos é que eles podem documentar a intenção de um determinado valor.
Voltando ao exemplo de `Complex` , poderia também ter definido coordenadas polares 2D como um tipo definido pelo utilizador:

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

Apesar de ambos `Complex` e ambos terem um tipo `Polar` `(Double, Double)` subjacente, os dois tipos são totalmente incompatíveis em Q#, minimizando o risco de acidentalmente chamar uma função matemática complexa com coordenadas polares e vice-versa.

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Aceda a itens anónimos com o operador de desembrulhar

Para aceder a itens anónimos, extrair primeiro o valor embrulhado utilizando o operador de pós-estação `!` .
Com o operador "desembrulhar", `!` pode extrair o valor contido num tipo definido pelo utilizador.
O tipo de expressão "desembrulhar" é o tipo subjacente do tipo definido pelo utilizador. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

Um único operador desembrulha uma camada de embrulho. Utilize vários operadores de desembrulhar para aceder a um valor multiplicado.

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

Para obter mais informações sobre o operador de desembrulhar, consulte [As Expressões tipo em Q#](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Criação de valores de tipos definidos pelo utilizador

Criar valores de um tipo definido pelo utilizador chamando o construtor de tipo correspondente:

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Em alternativa, pode criar novos valores a partir dos existentes utilizando [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Tal como fazem com as matrizes, as expressões de cópia e atualização copiam todos os valores de produto da expressão original, exceto nos itens nomeados especificados. Para estas exceções, os valores destes itens são os valores definidos no lado direito da expressão. Quaisquer outras construções linguísticas que estejam disponíveis para itens de matriz, por [exemplo, declarações de atualização e reatribuição,](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)existem para itens nomeados em tipos definidos pelo utilizador também.

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

* Pode utilizar tipos definidos pelo utilizador em qualquer lugar que utilize outros tipos.
Em particular, é possível definir uma matriz de um tipo definido pelo utilizador e incluir um tipo definido pelo utilizador como elemento de um tipo de tuple.

* Não é possível criar estruturas de tipo recursivo.
Ou seja, o tipo que define um tipo definido pelo utilizador não pode ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.
De uma forma mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas uns dos outros, pelo que o seguinte conjunto de definições de tipo é inválido:

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Tipos de funcionamento e função

Dados os tipos `'Tinput` `'Tresult` e:

* `('Tinput => 'Tresult)`é o tipo básico para qualquer *operação,* por `((Qubit, Pauli) => Result)` exemplo.
* `('Tinput -> 'Tresult)`é o tipo básico para qualquer *função,* por `(Int -> Int)` exemplo. 

Estes são chamados a *assinatura* do chamado.

* Todos os callables Q# têm um único valor como entrada e devolvem um único valor como saída.
* Pode utilizar tuples tanto para os valores de entrada como para a saída.
* Calíveis que não têm resultado, `Unit` devolvam.
* Os callables que não têm entrada tomam a tuple vazia como entrada.

### <a name="functors"></a>Functors

Os tipos *de função* são completamente especificados pela sua assinatura. Por exemplo, uma função que calcula o seno de um ângulo teria tipo `(Double -> Double)` . 

*As operações* têm determinadas características adicionais que são expressas como parte do tipo de operação. Essas características incluem informações sobre *quais os funtores que* a operação suporta.
Por exemplo, se a execução da operação depender do estado de outros qubits, então deve apoiar o `Controlled` functor; se a operação tiver um inverso, então deve apoiar o `Adjoint` functor.

> [!NOTE]
> Este artigo só discute como os funtores alteram a assinatura da operação. Para obter mais detalhes sobre functors e operações, consulte [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions). 

Para necessitar de suporte para o `Controlled` e/ou `Adjoint` functor num tipo de operação, é necessário adicionar uma anotação que indique as características correspondentes.
A anotação `is Ctl` (por `(Qubit => Unit is Ctl)` exemplo,) indica que a operação é controlável. Ou seja, a sua execução depende do estado de outro qubit ou qubits. Da mesma forma, a anotação `is Adj` indica que a operação tem um adjacente, ou seja, pode ser "invertida" de tal forma que aplicar sucessivamente uma operação e, em seguida, o seu contíguo a um estado deixa o estado inalterado. 

Se quiser exigir que uma operação deste tipo suporte tanto o `Adjoint` `Controlled` functor como o functor, pode expressar isto como `(Qubit => Unit is Adj + Ctl)` . Por exemplo, a operação Pauli incorporada <xref:microsoft.quantum.intrinsic.x> tem tipo `(Qubit => Unit is Adj + Ctl)` . 

Um tipo de operação que não suporta nenhum functor é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.

### <a name="type-parameterized-functions-and-operations"></a>Funções e operações por tipo-parametrizadas

Os tipos de caloisos podem conter *parâmetros de tipo*.
Utilizar um símbolo prefixado por uma única citação para indicar um parâmetro do tipo; por exemplo, `'A` é um parâmetro de tipo legal.
Para obter mais informações e detalhes sobre como definir calcários por parâmetros, consulte [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).

Um parâmetro do tipo pode aparecer mais de uma vez numa única assinatura.
Por exemplo, uma função que aplica outra função a cada elemento de uma matriz e devolve os resultados recolhidos tem a assinatura `(('A[], 'A->'A) -> 'A[])` .
Da mesma forma, uma função que devolve a composição de duas operações tem a assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Quando invoca um tipo de chamada parametrizada, todos os argumentos que tenham o mesmo parâmetro do tipo devem ser do mesmo tipo.

Q# não fornece um mecanismo para limitar os tipos possíveis que um utilizador pode substituir por um parâmetro do tipo.

## <a name="next-steps"></a>Passos seguintes

Agora que viu todos os tipos que compõem a linguagem Q#, consulte [Expressões tipo em Q#](xref:microsoft.quantum.guide.expressions) para aprender a criar e manipular expressões destes vários tipos.
