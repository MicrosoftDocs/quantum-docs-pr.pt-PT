---
title: Tipos em Q#
description: Saiba mais sobre os diferentes tipos utilizados na linguagem de programação Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: f7a3ac3813966c0ef695068297ce4d9949ead554
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327293"
---
# <a name="types-in-q"></a>Tipos em Q#

Esta página define o modelo do tipo Q# e descreve a sintaxe para especificar e trabalhar com tipos.
Na página seguinte, [Tipo Expressões,](xref:microsoft.quantum.guide.expressions)detalha como criar e operar em expressões deste tipo.

Notamos que Q# é uma linguagem *fortemente dactilografada,* de modo que o uso cuidadoso destes tipos pode ajudar o compilador a fornecer garantias fortes sobre os programas Q# no momento da compilação.
Para fornecer as garantias mais fortes possíveis, as conversões entre os tipos em Q# devem ser explícitas utilizando chamadas para funções que expressem essa conversão. Uma variedade de tais funções são fornecidas como parte do espaço de <xref:microsoft.quantum.convert> nome.
Por outro lado, os upcasts para tipos compatíveis acontecem implicitamente. 

Q# fornece ambos os tipos primitivos, que podem ser usados diretamente, e uma variedade de maneiras de produzir novos tipos de outros tipos.
Descrevemos cada um no resto desta secção.

## <a name="primitive-types"></a>Tipos Primitivos

A língua Q# fornece vários *tipos primitivos,* a partir dos quais outros tipos podem ser construídos:

- O `Int` tipo representa um número inteiro assinado de 64 bits, por exemplo: . . `2` . . . `107` `-5` .
- O `BigInt` tipo representa um número inteiro assinado de tamanho arbitrário, por `2L` `107L` exemplo, . `-5L` .
   Este tipo baseia-se no .NET<xref:System.Numerics.BigInteger>
   tipo.
- O `Double` tipo representa um número de ponto flutuante de dupla precisão, por exemplo: `0.0` . . . `-1.3` `4e-7` .
- O `Bool` tipo representa um valor Boolean que pode ser ou `true` `false` .
- O `Range` tipo representa uma sequência de inteiros, denotada `start..step..stop` por, onde denotar o passo é opcional. 
   Isto corresponde a , e por `start .. stop` `start..1..stop` exemplo, `1..2..7` representa a sequência $ \{ 1, 3, 5, 7 \} $.
- O `String` tipo é uma sequência de caracteres Unicode que é opaco para o utilizador uma vez criado.
  Este tipo é utilizado para reportar mensagens a um anfitrião clássico em caso de erro ou evento de diagnóstico.
- O `Unit` tipo é o tipo que permite apenas um `()` valor. 
  Este tipo é utilizado para indicar que a função Q# ou a operação não retorna nenhuma informação. 
- O `Qubit` tipo representa um bit quântico ou qubit.
   `Qubit`s são opacos para o utilizador; a única operação possível com eles, para além de passá-los para outra operação, é testar a identidade (igualdade).
   Em última análise, as ações em `Qubit` s são implementadas chamando instruções intrínsecas num processador quântico (ou uma simulação dos mesmos).
- O `Pauli` tipo representa um dos quatro operadores pauli de um único qubit.
   Este tipo é utilizado para denotar a operação base para rotações e especificar o que está a ser medido.
   Este é um tipo enumerado que tem quatro valores possíveis: `PauliI` `PauliX` , , `PauliY` `PauliZ` e, que são constantes de tipo `Pauli` .
- O `Result` tipo representa o resultado de uma medição.
   Este é um tipo enumerado com dois valores possíveis: `One` `Zero` e, que são constantes do tipo `Result` .
   `Zero`indica que o valor de +1 eigen foi medido; `One`indica o -1 eigenvalue.

As constantes `true` , , , , , , , e são `false` todos `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` símbolos reservados em Q#.

## <a name="array-types"></a>Tipos de Matrizes

Dado qualquer tipo Q# `'T` válido, existe um tipo que representa uma matriz de valores do tipo `'T` .
Este tipo de matriz é representado `'T[]` como; por exemplo, `Qubit[]` ou `Int[][]` .
Por exemplo, uma coleção de inteiros é denotada, `Int[]` enquanto uma variedade de matrizes de `(Bool, Pauli)` valores é denotada `(Bool, Pauli)[][]` .

No segundo exemplo, note que isto representa uma matriz potencialmente irregular de matrizes, e não uma matriz bidimensional retangular.
Q# não fornece suporte para matrizes multidimensionais retangulares.

Um valor de matriz pode ser escrito no código fonte Q# utilizando suportes quadrados em torno dos elementos de uma matriz, como em `[PauliI, PauliX, PauliY, PauliZ]` .
O tipo de matriz literal é determinado pelo tipo de base comum de todos os itens da matriz. Assim, tentar construir uma matriz com elementos que não têm um tipo de base comum levantará um erro.  
Consulte [as matrizes de chamadas](xref:microsoft.quantum.guide.expressions#arrays-of-callables) para um exemplo disso.

> [!WARNING]
> Os elementos de uma matriz não podem ser alterados após a criação da matriz.
> [As declarações de atualização e reatribuição](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) e/ou [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) podem ser usadas para construir uma matriz modificada.

Alternativamente, uma matriz pode ser criada a partir do seu tamanho usando a `new` palavra-chave:

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

Em qualquer dos casos, uma vez construída uma matriz, a função central `Length` pode ser usada para obter o número de elementos como `Int` .
As matrizes podem ser subscritadas utilizando suportes quadrados, com subscritos com tipo `Int` ou `Range` tipo, para obter elementos únicos ou novos arrays que contenham um subconjunto dos elementos de uma matriz.
Os subscritos de matrizes são baseados em zero:

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>Tipos tuple

Dado zero ou mais tipos `T0` `T1` diferentes, podemos `Tn` denotar um novo *tipo de tuple* como `(T0, T1, ..., Tn)` .
Os tipos usados para construir um novo tipo de tuple podem ser tuples, como em `(Int, (Qubit, Qubit))` .
No entanto, esse nidificação é sempre finito, uma vez que os tipos de tuple não podem, em circunstância alguma, conter-se.

Os valores do novo tipo tuple são tuples formados por sequências de valores de cada tipo no tuple.
Por exemplo, `(3, false)` é um tuple cujo tipo é o tipo tuple `(Int, Bool)` .
É possível criar matrizes de tuples, tuples de matrizes, tuples de sub-tuples, etc.

A partir de Q# 0.3, `Unit` é o nome do *tipo* de tuple vazio; é usado para `()` o *valor*de tuple vazio .

As instâncias de tuple são imutáveis.
Q# não fornece um mecanismo para alterar o conteúdo de um tuple uma vez criado.

Tuples é um conceito poderoso usado ao longo de Q# para recolher valores juntos em um único valor, tornando mais fácil passá-los ao redor.
Em particular, usando a notação de tuple, podemos expressar que cada operação e callable leva exatamente uma entrada e devolve exatamente uma saída.

### <a name="singleton-tuple-equivalence"></a>Equivalência de Tuple Singleton

É possível criar um tuple singleton (single-element), `('T1)` como `(5)` ou `([1,2,3])` .
No entanto, Q# trata um tuple singleton como completamente equivalente a um valor do tipo fechado.
Ou seja, não há diferença entre `5` `(5)` e, ou entre `5` `(((5)))` e, ou entre `(5, (6))` e `(5, 6)` .
É igualmente válido escrever `(5)+3` como `5+3` escrever, e ambas as expressões irão avaliar para `8` .

Esta equivalência aplica-se para todos os efeitos, incluindo atribuição e expressões.
Dada qualquer expressão, a mesma expressão em anexo em parênteses é uma expressão do mesmo tipo.
Por exemplo, `(7)` é uma `Int` expressão, é uma expressão do tipo `([1,2,3])` de matriz de `Int` s, e é uma expressão com tipo `((1,2))` `(Int, Int)` .

Isto significa, em particular, que uma operação ou função cujo tipo de tuple de entrada ou de saída tem um campo pode ser considerado como tendo um único argumento ou devolvendo um único valor.

Referimo-nos a esta propriedade como _equivalência de tuple singleton._


## <a name="user-defined-types"></a>Tipos definidos pelo utilizador

Uma declaração de tipo definido pelo utilizador consiste na `newtype` palavra-chave, seguida do nome do tipo definido pelo utilizador, `=` uma especificação de tipo válido e um ponto de terminação.

Por exemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```

Cada ficheiro de origem Q# pode declarar qualquer número de tipos definidos pelo utilizador.
Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento e os nomes das funções.

Os tipos definidos pelo utilizador são distintos mesmo que os tipos de base sejam idênticos.
Em particular, não existe uma conversão automática entre valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.

### <a name="named-vs-anonymous-items"></a>Nomeados vs. itens anónimos

Um ficheiro Q# pode definir um novo tipo nomeado contendo um único valor de qualquer tipo legal.
Para qualquer tipo de `T` tuple, podemos declarar um novo tipo definido pelo utilizador que é um subtipo de `T` com a `newtype` declaração.
No @"microsoft.quantum.math" espaço de nomes, por exemplo, os números complexos são definidos como um tipo definido pelo utilizador:

```qsharp
newtype Complex = (Double, Double);
```
Esta afirmação cria um novo tipo com dois itens anónimos do tipo `Double` .   

Além de itens anónimos, os tipos definidos pelo utilizador também *suportam itens nomeados* a partir da versão Q# 0.7 ou superior. Por exemplo, poderíamos ter nomeado os itens `Re` para o duplo representando a parte real de um número complexo e para a parte `Im` imaginária: 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Nomear um item num tipo definido pelo utilizador não implica que todos os itens precisem de ser nomeados - qualquer combinação de itens nomeados e não nomeados é suportada. Além disso, os itens internos também podem ser nomeados.
O tipo `Nested` definido abaixo, por exemplo, tem um tipo `(Double, (Int, String))` subjacente, do qual apenas o item do tipo `Int` é nomeado e todos os outros itens são anónimos. 

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
Desta forma, os tipos definidos pelo utilizador têm um papel semelhante ao Records em F# por exemplo. 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>Aceda a itens anónimos com o operador de desembrulhar

Por outro lado, para aceder a itens anónimos, o valor embrulhado tem primeiro de ser extraído através do operador de pós-estan `!` fixação .
O operador "desembrulhar", `!` permite extrair o valor contido num tipo definido pelo utilizador.
O tipo de expressão "desembrulhar" é o tipo subjacente do tipo definido pelo utilizador. 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

O operador desembrulha exatamente uma camada de embrulho.
Vários operadores de desembrulhásse podem ser utilizados para aceder a um valor multiplicado.

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

Mais detalhes sobre o operador de desembrulhar podem ser [encontrados em Expressões Tipo em Q#](xref:microsoft.quantum.guide.expressions).

### <a name="creating-values-of-user-defined-types"></a>Criação de valores de tipos definidos pelo utilizador

Os valores de um tipo definido pelo utilizador podem ser criados chamando o construtor de tipo correspondente:

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

Alternativamente, novos valores podem ser criados a partir dos existentes usando [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). Tal como para as matrizes, tais expressões copiam todos os valores de item da expressão original, com exceção dos itens nomeados especificados. Para estes os valores são definidos no lado direito da expressão. Quaisquer outras construções linguísticas, como por [exemplo, declarações de atualização e reatribuição,](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)que estejam disponíveis para itens de matriz existem para itens nomeados em tipos definidos pelo utilizador também.

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

Os tipos definidos pelo utilizador podem ser utilizados em qualquer outro tipo que possa ser utilizado.
Em particular, é possível definir uma matriz de um tipo definido pelo utilizador e incluir um tipo definido pelo utilizador como elemento de um tipo de tuple.

Nota não é possível criar estruturas de tipo recursivo.
Ou seja, o tipo que define um tipo definido pelo utilizador pode não ser um tipo de tuple que inclua um elemento do tipo definido pelo utilizador.
De um modo mais geral, os tipos definidos pelo utilizador podem não ter dependências cíclicas uns dos outros, pelo que o seguinte conjunto de definições de tipo seria ilegal:

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Tipos de funcionamento e função

O tipo básico para qualquer chamada é escrito como `('Tinput => 'Tresult)` `('Tinput -> 'Tresult)` ou, onde ambos `'Tinput` e são `'Tresult` tipos.
Estes são chamados a *assinatura* do chamado.

Todos os callables Q# são considerados para ter um único valor como entrada e devolver um único valor como saída.
Tanto os valores de entrada como de saída podem ser tuples.
Calíveis que não têm retorno de `Unit` resultados .
Os callables que não têm entrada tomam a tuple vazia como entrada.

> [!NOTE]
> O primeiro formulário, `=>` com, é usado para operações; o segundo formulário, `->` com, para funções.
> Por exemplo, `((Qubit, Pauli) => Result)` representa a assinatura para uma possível operação de medição de um único qubit.
Os tipos *de função* são completamente especificados pela sua assinatura.
Por exemplo, uma função que calcula o seno de um ângulo teria tipo `(Double -> Double)` .

*As operações*---mas não funcionam---se de certas características adicionais que são expressas como parte do tipo de funcionamento. Essas características incluem informações sobre os *funtores* que a operação suporta.
Por exemplo, se a execução da operação pode ser condicionada ao estado de outros qubits, deve apoiar o `Controlled` functor; se a operação tiver um inverso, deve apoiar o `Adjoint` functor. Os funtores e operações são discutidos em detalhe em [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions), mas aqui simplesmente discutimos como isso altera a assinatura da operação.

Para exigir apoio ao `Controlled` e/ou `Adjoint` functor num tipo de operação, precisamos de adicionar uma anotação indicando as características correspondentes.
Uma anotação `is Ctl` (por `(Qubit => Unit is Ctl)` exemplo) indica que a operação é controlável---é que é, é a execução condicionada ao estado de outro qubit ou qubits. Da mesma forma, `is Adj` indica que a operação tem um adjacente; ou simplesmente, pode ser "invertida" de tal forma que aplicar sucessivamente uma operação e, em seguida, o seu contíguo a um estado deixa o estado inalterado. 

Se quisermos exigir que uma operação desse tipo suporte tanto o `Adjoint` `Controlled` functor como o functor, podemos expressar isto como `(Qubit => Unit is Adj + Ctl)` . Por exemplo, a operação Pauli incorporada <xref:microsoft.quantum.intrinsic.x> tem tipo `(Qubit => Unit is Adj + Ctl)` . 

Um tipo de operação que não suporta nenhum functor é especificado apenas pelo seu tipo de entrada e saída, sem anotação adicional.

### <a name="type-parameterized-functions-and-operations"></a>Funções e operações por tipo-parametrizadas

Os tipos de caloisos podem conter parâmetros de tipo.
Os parâmetros do tipo são indicados por um símbolo prefixado por uma única cotação; por exemplo, `'A` é um parâmetro de tipo legal.
Os detalhes sobre a definição de calcários por tipo são fornecidos na página [Operações e Funções na página Q#.](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)

Um parâmetro do tipo pode aparecer mais de uma vez numa única assinatura.
Por exemplo, uma função que aplique outra função a cada elemento de uma matriz e devolva os resultados recolhidos teria assinatura `(('A[], 'A->'A) -> 'A[])` .
Da mesma forma, uma função que retorne a composição de duas operações pode ter assinatura `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .

Ao invocar um tipo de pôr tipo-paradizável, todos os argumentos que tenham o mesmo parâmetro do tipo devem ser do mesmo tipo.

Q# não fornece um mecanismo para limitar os tipos possíveis que podem ser substituídos por um parâmetro do tipo.

## <a name="next-steps"></a>Próximos passos

Agora que viu todos os tipos que compõem a linguagem Q#, pode dirigir-se a [Expressãos tipo em Q#](xref:microsoft.quantum.guide.expressions) para ver como criar e manipular expressões destes vários tipos.


