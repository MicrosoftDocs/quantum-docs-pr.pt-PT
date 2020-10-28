---
title: Expressões em Q#
description: Compreender como especificar, referenciar e combinar constantes, variáveis, operadores, operações e funções como expressões em Q# .
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691595"
---
# <a name="expressions-in-no-locq"></a>Expressões em Q#

## <a name="numeric-expressions"></a>Expressões numéricas

Expressões numéricas são expressões do `Int` `BigInt` tipo, ou `Double` .
Ou seja, ou são números inteiros ou de pontos flutuantes.

`Int` literais Q# são escritos como uma sequência de dígitos.
Os inteiros hexadecimais e binários são suportados e escritos com um `0x` `0b` prefixo, respectivamente.

`BigInt` literais em Q# ter um rasto ou `l` `L` sufixo.
Os grandes inteiros hexadecimais são suportados e escritos com um prefixo "0x".
Assim, todas são utilizações válidas de `BigInt` literais:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` literais são Q# números de ponto flutuante escritos usando dígitos decimais.
Podem ser escritos com ou sem ponto decimal, `.` ou uma parte exponencial indicada com 'e' ou 'E' (após o qual apenas são válidos um possível sinal negativo e dígitos decimais).
Seguem-se `Double` literais válidos: `0.0` . . . `1.2e5` `1e-5` .

Dada a expressão de matriz de qualquer tipo de elemento, pode formar uma `Int` expressão utilizando a [`Length`](xref:Microsoft.Quantum.Core.Length) função incorporada, com a expressão de matriz fechada em parênteses.
Por exemplo, se `a` estiver ligado a uma matriz, então é uma expressão `Length(a)` inteiro.
Se `b` for uma matriz de inteiros, `Int[][]` então é o número de `Length(b)` sub-matrizes em `b` , e é o número de `Length(b[1])` inteiros na segunda sub-matriz em `b` .

Tendo em conta duas expressões numéricas do mesmo tipo, os operadores `+` `-` `*` binários, e `/` podem ser usados para formar uma nova expressão numérica.
O tipo de nova expressão é o mesmo que os tipos de expressões constituintes.

Tendo em conta duas expressões mais recentes, utilize o operador binário `^` (potência) para formar uma nova expressão de inteiro.
Da mesma forma, você também pode usar `^` com duas expressões duplas para formar uma nova expressão dupla.
Finalmente, você pode usar `^` com um grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão de inteiro.
Neste caso, o segundo parâmetro deve encaixar em 32 bits; caso contrário, levanta um erro de tempo de execução.

Tendo em conta duas expressões inteiros ou grandes, formam uma nova expressão inteiro ou grande, utilizando os `%` operadores (modulus), `&&&` (bitwise E), `|||` (bitwise OR) ou `^^^` (bitwise XOR).

Dada a expressão de um inteiro ou de um grande inteiro à esquerda, e uma expressão inteiro à direita, use os `<<<` operadores (mudança aritmética à esquerda) ou `>>>` (mudança de direita aritmética) para criar uma nova expressão com o mesmo tipo que a expressão da esquerda.

O segundo parâmetro (a quantidade de turno) para uma operação por turnos deve ser superior ou igual a zero; o comportamento para quantidades de turno negativas é indefinido.
O valor de deslocação para qualquer operação por turnos também deve caber em 32 bits; caso contrário, levanta um erro de tempo de execução.
Se o número alterado for um número inteiro, então o valor do turno é `mod 64` interpretado; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.

Tanto para os valores inteiros como para os grandes valores inteiros, as mudanças são aritmética.
Deslocar um valor negativo, tanto à esquerda como à direita, resulta num número negativo.
Ou seja, deslocar um passo para a esquerda ou para a direita é o mesmo que multiplicar ou dividir por 2, respectivamente.

A divisão de inteiros e o módulo inteiro seguem o mesmo comportamento para números negativos como C#. Ou seja, `a % b` tem sempre o mesmo sinal que , e sempre `a` `b * (a / b) + a % b` `a` igual. Por exemplo:

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| 5 | 2 | 2 | 1 |
| 5 | -2 | -2 | 1 |
| -5 | 2 | -2 | -1 |
| -5 | -2 | 2 | -1 |

A grande divisão de inteiros e as operações de módulos funcionam da mesma forma.

Dada qualquer expressão numérica, pode formar uma nova expressão usando o `-` operador unary.
A nova expressão é do mesmo tipo que a expressão constituinte.

Dada qualquer expressão inteiro ou grande, pode formar uma nova expressão do mesmo tipo utilizando o `~~~` operador (pequeno complemento) unary.

## <a name="boolean-expressions"></a>Expressões booleanas

Os dois `Bool` valores literais são `true` `false` e.

Tendo em conta duas expressões do mesmo tipo primitivo, os `==` `!=` operadores binários podem ser utilizados para construir uma `Bool` expressão.
A expressão é verdadeira se as duas expressões forem iguais e falsas se não.

Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores desembrulhados podem ser comparados. Por exemplo, utilizando o operador "desembrulhar" `!` (explicado em pormenor na [Types Q# in ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

A comparação entre igualdade de `Qubit` valores é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.
Os estados dos dois qubits não são comparados, acedidos, medidos ou modificados por esta comparação.

A comparação entre a igualdade e `Double` os valores pode ser enganosa devido aos efeitos de arredondamento.
Por exemplo, `49.0 * (1.0/49.0) != 1.0`.

Tendo em conta duas expressões numéricas, os operadores binários `>` , e podem ser `<` `>=` `<=` usados para construir uma nova expressão booleana que é verdade se a primeira expressão for respectivamente maior do que, menos do que, maior ou igual a, ou inferior ou igual à segunda expressão.

Dadas as duas expressões booleanas, use o `and` operador binário para construir uma nova expressão booleana que é verdade se ambas as expressões forem verdadeiras. Da mesma forma, a utilização do `or` operador cria uma expressão que é verdadeira se uma das duas expressões for verdadeira.

Dada qualquer expressão booleana, o `not` operador unary pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.

## <a name="string-expressions"></a>Expressões de cadeia

Q# permite que as cordas sejam utilizadas na `fail` declaração (explicada no [Fluxo de Controlo)](xref:microsoft.quantum.guide.controlflow#fail-statement)e na [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) função padrão. O comportamento específico deste último depende do simulador utilizado, mas normalmente escreve uma mensagem para a consola anfitriã quando é chamado durante um Q# programa.

As cordas Q# são literais ou cordas interpoladas.

As letras de corda são semelhantes às simples cordas literais na maioria das línguas: uma sequência de caracteres Unicode incluídos em citações duplas `" "` .
Dentro de uma corda, use o personagem de backslash `\` para escapar a um personagem de dupla citação `\"` (), ou para inserir uma nova linha ( ), um retorno de `\n` transporte ( ) ou um `\r` separador ( ). `\t`
Por exemplo:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Cordas interpoladas

A Q# sintaxe para interpolações de cordas é um subconjunto da sintaxe C#. Seguem-se os pontos-chave que dizem respeito Q# a:

* Para identificar uma corda literal como uma corda interpolada, prepare-a com o `$` símbolo. Não pode haver espaço branco entre o `$` e o que começa uma corda `"` literal.

* O seguinte é um exemplo básico usando a [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) função para escrever o resultado de uma medição para a consola, ao lado de Q# outras expressões.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* Qualquer expressão válida Q# pode aparecer numa corda interpolada.

* Expressões dentro de uma corda interpolada seguem Q# a sintaxe, não a sintaxe C#. A distinção mais notável é que Q# não suporta cordas interpoladas verbatim (multi-line).

Para obter mais detalhes sobre a sintaxe C#, consulte [*As Cordas Interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).

## <a name="range-expressions"></a>Expressões de alcance

Tendo em conta as três `Int` expressões `start` , e , a expressão é uma expressão de alcance cujo primeiro elemento é , o `step` segundo elemento é , o terceiro elemento é `stop` , e assim `start .. step .. stop` `start` `start+step` por `start+step+step` diante, até `stop` passar.
Uma gama pode estar vazia se, por exemplo, `step` for positiva e . `stop < start` .

O alcance é inclusivo em ambas as extremidades. Ou seja, se a diferença entre `start` e é um conjunto inteiro `stop` `step` de, o último elemento da gama será `stop` .

Tendo em conta `Int` duas expressões `start` `stop` e, a expressão `start .. stop` é uma expressão de alcance que é igual a `start .. 1 .. stop` .
Note que o implícito `step` é +1 mesmo que `stop` seja `start` inferior; em tal caso, o intervalo está vazio.

Algumas gamas de exemplos são:

- `1..3` é o alcance 1, 2, 3.
- `2..2..5` é o alcance 2, 4.
- `2..2..6` é o alcance 2, 4, 6.
- `6..-2..2` é o alcance 6, 4, 2.
- `2..1` é o alcance vazio.
- `2..6..7` é o alcance 2.
- `2..2..1` é o alcance vazio.
- `1..-1..2` é o alcance vazio.

## <a name="qubit-expressions"></a>Expressões qubit

As `Qubit` únicas expressões são símbolos que estão ligados a `Qubit` valores ou elementos de `Qubit` matrizes.
Não há `Qubit` literais.

## <a name="pauli-expressions"></a>Expressões Pauli

Os quatro `Pauli` valores são `PauliI` `PauliX` `PauliY` `PauliZ` `Pauli` expressões válidas.

Para além disso, as `Pauli` únicas expressões são símbolos que estão ligados a `Pauli` valores ou elementos de `Pauli` matrizes.

## <a name="result-expressions"></a>Expressões de resultados

Os dois `Result` `One` valores, `Zero` e, são `Result` expressões válidas.

Para além disso, as `Result` únicas expressões são símbolos que estão ligados a `Result` valores ou elementos de `Result` matrizes.
Em particular, note que não é o mesmo que `One` o inteiro , e não há conversão direta entre `1` eles.
O mesmo se aplica `Zero` `0` e. .

## <a name="tuple-expressions"></a>Expressões tuple

Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas em parênteses.
Por exemplo, `(1, One)` é uma `(Int, Result)` expressão.

Além das literais, as únicas expressões de tuple são símbolos que são obrigados a tuple valores, elementos de matrizes de tuple, e invocações callable que devolvem tuples.

## <a name="user-defined-type-expressions"></a>Expressões User-Defined tipo

Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.
Por exemplo, se `IntPair` for um tipo definido pelo utilizador baseado em , `(Int, Int)` então é um literal válido desse `IntPair(2, 3)` tipo.

Além das literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos de matrizes desse tipo, e invocações pôveis que devolvem esse tipo.

## <a name="unwrap-expressions"></a>Desembrulhar expressões

Em Q# , o operador de desembrulhamento é um ponto de exclamação de fuga `!` .
Por exemplo, se `IntPair` for um tipo definido pelo utilizador com o tipo subjacente e é uma `(Int, Int)` `s` variável com `IntPair(2, 3)` valor, então `s!` é `(2, 3)` .

Para os tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador, pode repetir o operador de desembrulhá-lo. Por exemplo, `s!!` indica o valor duplamente desembrulhado de `s` .
Assim, se `WrappedPair` for um tipo definido pelo utilizador com tipo `IntPair` subjacente, e é uma `t` variável com `WrappedPair(IntPair(1,2))` valor, então `t!!` é `(1,2)` .

O `!` operador tem uma precedência mais elevada do que todos os outros operadores que não para a `[]` indexação e corte de matrizes.
`!` e `[]` ligar posicionalmente; ou seja, `a[i]![3]` lê-se como `((a[i])!)[3]` : pegue no elemento de , `i` `a` desembrulhe-o e, em seguida, obtenha o terceiro elemento do valor desembrulhado (que deve ser uma matriz).

A precedência do `!` operador tem um impacto que pode não ser óbvio.
Se uma função ou operação devolver um valor que seja desembrulhado, a função ou chamada de funcionamento deve ser fechada em parênteses para que o argumento se ligue à chamada e não ao desembrulho.
Por exemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expressões de matriz

Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas em suportes quadrados `[]` .
Todos os elementos devem ser compatíveis com o mesmo tipo.

Tendo em conta duas matrizes do mesmo tipo, utilize o operador binário `+` para formar uma nova matriz que é a concatenação das duas matrizes.
Por exemplo, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Criação de Matrizes

Dado um tipo e uma `Int` expressão, utilize o `new` operador para alocar uma nova matriz do tamanho dado.
Por exemplo, `new Int[i + 1]` atribui uma nova matriz com `Int` `i + 1` elementos.

Não são permitidos conjuntos literais vazios, tais `[]` como, não são permitidos.
Em vez disso, pode criar uma matriz de comprimento zero utilizando `new T[0]` , onde é reservado para um tipo `T` adequado.

Os elementos de uma nova matriz inicializam-se a um valor predefinido dependente do tipo.
Na maioria dos casos, esta é uma variação de zero.

Para qubits e callables, que são referências a entidades, não existe um valor padrão razoável.
Assim, para estes tipos, o padrão é uma referência inválida que não pode utilizar sem causar um erro de tempo de execução, semelhante a uma referência nula em idiomas como C# ou Java.
Os conjuntos que contenham qubits ou calcáveis devem ser rubricados com valores não predefinidos antes de poder utilizar os seus elementos com segurança. Para rotinas de inicialização adequadas, consulte <xref:Microsoft.Quantum.Arrays> .

Os valores predefinidos para cada tipo são:

Tipo | Predefinição
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _qubit inválido_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | A gama vazia, `1..1..0`
 `Callable` | _inválido callable_
 `Array['T]` | `'T[0]`

Os tipos de tuple inicializam elemento por elemento.


### <a name="array-elements"></a>Elementos de matriz

Dada a expressão de matriz e uma `Int` expressão, forme uma nova expressão utilizando o operador de elemento de matriz `[]` .
A nova expressão é do mesmo tipo que o tipo de elemento da matriz.
Por exemplo, se `a` estiver ligado a uma matriz de `Double` tipo, então `a[4]` é uma `Double` expressão.

Se a expressão da matriz não for um identificador simples, deve pliá-la em parênteses para selecionar um elemento.
Por exemplo, se `a` e `b` são ambas matrizes do `Int` tipo, um elemento da concatenação é expresso como:

```qsharp
(a + b)[13]
```

Todos os conjuntos são baseados em Q# zero.
Ou seja, o primeiro elemento de uma matriz `a` é `a[0]` sempre.


### <a name="array-slices"></a>Fatias de Matriz

Dada a expressão de matriz e uma `Range` expressão, forme uma nova expressão utilizando o operador de fatias de matriz `[ ]` .
A nova expressão é do mesmo tipo que a matriz e contém os itens de matriz indexados pelos elementos do `Range` , na ordem definida pelo `Range` .
Por exemplo, se `a` estiver ligado a uma matriz de `Double` tipo, então `a[3..-1..0]` é uma expressão que contém os `Double[]` primeiros quatro elementos de `a` mas na ordem inversa como aparecem em `a` .

Se a `Range` fatia de matriz estiver vazia, então a fatia de matriz resultante tem um comprimento zero.

Tal como acontece com os elementos de matriz de referência, se a expressão da matriz não for um simples identificador, deve pliá-la em parênteses para a cortar.
Por exemplo, se `a` e `b` são ambos conjuntos de `Int` tipo, uma fatia da concatenação é expressa como:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valores inferidos de início/fim

Começando com o nosso [lançamento 0.8,](xref:microsoft.quantum.relnotes)apoiamos expressões contextuais para corte de alcance. Em particular, pode omitir valores de início e fim de alcance no contexto de uma expressão de corte de gama. Nesse caso, o compilador aplica as seguintes regras para inferir os delimitadores previstos para o intervalo:

* Se o valor *inicial* do intervalo for omitido, então o valor inicial inferido
  * é zero se não for especificado nenhum passo ou se o passo especificado for positivo.  
  * é o comprimento da matriz fatiada menos um se o passo especificado for negativo.

* Se o valor *final* da gama for omitido, então o valor final inferido
  * é o comprimento da matriz fatiada menos um se não for especificado nenhum passo ou se o passo especificado for positivo.
  * é zero se o passo especificado for negativo.

Alguns exemplos incluem:

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>Expressões de cópia e atualização

Uma vez que todos os Q# tipos são tipos de valor (com os qubits a assumirem um papel um pouco especial), formalmente é criada uma "cópia" quando um valor está ligado a um símbolo ou quando um símbolo é recuperado. Ou seja, o comportamento Q# é o mesmo que se uma cópia fosse criada usando um operador de atribuição. 

Claro que, na prática, apenas as peças relevantes são recriadas conforme necessário. Isto afeta a forma como copia os arrays porque não é possível atualizar itens de matriz. Modificar uma matriz existente requer uma alavancagem de um mecanismo *de cópia e atualização.*

Pode criar uma nova matriz a partir de uma matriz existente através de expressões *de cópia e atualização,* que utilizam os operadores `w/` e `<-` .
Uma expressão de cópia e atualização é uma expressão da `expression1 w/ expression2 <- expression3` forma, onde

* `expression1` deve ser tipo `T[]` para algum tipo `T` .
* `expression2` define quais os índices na matriz `expression1` especificados para modificar. `expression2` deve ser do tipo `Int` ou do tipo `Range` .
* `expression3` é o valor(s) utilizado para atualizar elementos `expression1` em , com base nos índices especificados em `expression2` . Se `expression2` for do `Int` tipo, deve ser do tipo `expression3` `T` . Se `expression2` for do `Range` tipo, deve ser do tipo `expression3` `T[]` .

Por exemplo, a expressão de cópia e atualização `arr w/ idx <- value` constrói um novo conjunto com todos os elementos definidos para os elementos correspondentes em , exceto nos `arr` elementos(s) especificados por `idx` , que é definido como valor(s) em `value` . 

Dado `arr` contém a `[0,1,2,3]` matriz, então 

- `arr w/ 0 <- 10` é a matriz `[10,1,2,3]` .
- `arr w/ 2 <- 10` é a matriz `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]` é a matriz `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Expressões de cópia e atualização para itens nomeados

Expressões semelhantes existem para itens nomeados em tipos definidos pelo utilizador. 

Por exemplo, considere o tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Se `c` contiver o valor do `Complex(1., -1.)` tipo, então `c w/ Re <- 0.` é uma expressão do tipo que avalia `Complex` `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Matrizes irregulares

Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes.
Os elementos de uma matriz irregular podem ser de diferentes tamanhos.
O exemplo a seguir mostra como declarar e inicializar uma matriz irregular que representa uma tabela de multiplicação.

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Matrizes de callables 

Também pode criar uma variedade de chamadas.

* Se o tipo de elemento comum for um tipo de funcionamento ou função, todos os elementos devem ter os mesmos tipos de entrada e saída.
* O tipo de elemento da matriz suporta quaisquer funtores que sejam [suportados](xref:microsoft.quantum.guide.operationsfunctions) por todos os elementos.
Por exemplo, se `Op1` , e todos são `Op2` `Op3` `Qubit[] => Unit` operações, mas `Op1` `Adjoint` suportes, `Op2` suportes , e apoia `Controlled` `Op3` ambos:
  * `[Op1, Op2]` é uma série de `(Qubit[] => Unit)` operações.
  * `[Op1, Op3]` é uma série de `(Qubit[] => Unit is Adj)` operações.
  * `[Op2, Op3]` é uma série de `(Qubit[] => Unit is Ctl)` operações.

No entanto, embora as operações `(Qubit[] => Unit is Adj)` e tenham o tipo de base comum  `(Qubit[] => Unit is Ctl)` `(Qubit[] => Unit)` de, os *conjuntos destas* operações não partilham um tipo de base comum.

Por exemplo, `[[Op1], [Op2]]` atualmente levantaria um erro porque tenta criar um conjunto dos dois tipos de matrizes incompatíveis `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .

Para obter mais informações sobre chamadas, consulte [expressões calláveis](#callable-expressions) nesta página ou [Operações e Funções em Q# ](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="conditional-expressions"></a>Expressões Condicionais

Tendo em conta duas expressões do mesmo tipo e uma expressão booleana, formam uma expressão condicional utilizando o ponto de `?` interrogação, e a barra `|` vertical. Dado `a==b ? c | d` que o valor da expressão condicional é se é verdade e se é `c` `a==b` `d` falso.

### <a name="conditional-expressions-with-callables"></a>Expressões condicionais com callables

Expressões condicionais podem avaliar operações que tenham as mesmas entradas e saídas, mas suportam diferentes functors. Neste caso, o tipo de expressão condicional é uma operação com entradas e saídas que suportam quaisquer funtores apoiados por ambas as expressões.
Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:

- `flag ? Op1 | Op2` é uma `(Qubit[] => Unit)` operação.
- `flag ? Op1 | Op3` é uma `(Qubit[] => Unit is Adj)` operação.
- `flag ? Op2 | Op3` é uma `(Qubit[] => Unit is Ctl)` operação.

Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de funcionamento, essa chamada só ocorre se esse resultado for o valor da chamada. Por exemplo, no caso `a==b ? C(qs) | D(qs)` , se `a==b` for verdade, a `C` operação é invocada, e se for falsa, então apenas a `D` operação é invocada. Esta abordagem é semelhante ao *curto-circuito* noutras línguas.

## <a name="callable-expressions"></a>Expressões calláveis

Um literal chamado é o nome de uma operação ou função definida no âmbito de compilação. Por exemplo, `X` é uma operação literal que se refere à operação padrão da `X` biblioteca, e é uma `Message` função literal que se refere à função de biblioteca `Message` padrão.

Se uma operação suporta o `Adjoint` functor, então `Adjoint op` é uma expressão de operação.
Da mesma forma, se a operação suporta o `Controlled` functor, então `Controlled op` é uma expressão de operação.
Para obter mais informações sobre os tipos destas expressões, consulte [as especializações da operação Call](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Os functores `Adjoint` `Controlled` (e) ligam-se mais estreitamente do que todos os outros operadores, com exceção do operador de desembrulhar `!` e da indexação da matriz com `[ ]` .
Assim, todos são válidos, assumindo que as operações suportam os funtores utilizados:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Expressões de caloisos por tipo parametrizadas

Você pode usar um literal chamado como um valor, por exemplo, para atribuí-lo a uma variável ou passá-lo para outra chamada. Neste caso, se a chamada tiver [parâmetros de tipo,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)deve fornecer os parâmetros como parte do valor de chamada.

Um valor calável não pode ter parâmetros de tipo não especificados. Por exemplo, se `Fun` for uma função com a `'T1->Unit` assinatura:

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expressões de invocação callable

Dada a expressão callable (operação ou função) e uma expressão tuple do tipo de entrada da assinatura do callable, pode formar uma *expressão de invocação,* anexando a expressão de tuple à expressão callable.
O tipo de expressão de invocação é o tipo de saída da assinatura do callable.

Por exemplo, se `Op` for uma operação com a `((Int, Qubit) => Double)` assinatura, é uma expressão do tipo `Op(3, qubit1)` `Double` .
Da mesma forma, se `Sin` for uma função com a `(Double -> Double)` assinatura, é uma expressão do tipo `Sin(0.1)` `Double` .
Finalmente, se `Builder` é uma função com a `(Int -> (Int -> Int))` assinatura, então `Builder(3)` é uma função de `Int` `Int` .

Invocar o resultado de uma expressão de valor callable requer um par extra de parênteses em torno da expressão callable.
Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:

```qsharp
(Builder(3))(2)
```

Ao invocar uma chamada [tipo-parametrizada,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) pode especificar os parâmetros reais do tipo dentro dos suportes angulares `< >` após a expressão callable.
Esta ação é geralmente desnecessária, uma vez que o Q# compilador infere os tipos reais.
No entanto, *é* necessário para [a aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se um argumento porontose de tipo não for especificado.
Também é útil ao passar operações com diferentes suportes de functor para um callable.

Por exemplo, se `Func` tiver assinatura , e ter assinatura , e tiver assinatura , para invocar `('T1, 'T2, 'T1) -> 'T2` como primeiro `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` `Op1` argumento, como o `Op2` segundo, e como o `Op3` terceiro:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A especificação do tipo é necessária porque `Op3` e `Op1` tem diferentes tipos, de modo que o compilador tratará isto como ambíguo sem a especificação.


## <a name="operator-precedence"></a>Precedência do operador

* Todos os operadores binários são associados à direita, `^` exceto.

* Os `[ ]` suportes, para corte e indexação de matrizes, ligam-se perante qualquer operador.

* Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.

* Os parênteses para a invocação de funcionamento e função também se ligam perante qualquer operador, mas após a indexação de matrizes e funtores.

Q# Operadores por ordem de precedência, da mais alta para a mais baixa:

Operador | Arity | Descrição | Tipos operand
---------|----------|---------|---------------
 trailing `!` | Unário | Desembrulhar | Qualquer tipo definido pelo utilizador
 `-`, `~~~`, `not` | Unário | Numérico negativo, complemento bitwise, negação lógica | `Int`, `BigInt` ou `Double` `-` para, ou para `Int` `BigInt` `~~~` , `Bool``not`
 `^` | Binário | Poder inteiro | `Int` ou `BigInt` para a base, para o `Int` expoente
 `/`, `*`, `%` | Binário | Divisão, multiplicação, módulo inteiro | `Int`, `BigInt` ou `Double` para `/` `*` e, ou `Int` `BigInt` para `%`
 `+`, `-` | Binário | Adição ou cadeia e concatenação de matriz, subtração | `Int`, `BigInt` ou `Double` , adicionalmente ou qualquer tipo de matriz `String` para `+`
 `<<<`, `>>>` | Binário | Turno da esquerda, turno da direita | `Int` ou `BigInt`
 `<`, `<=`, `>`, `>=` | Binário | Comparações menos do que, menos ou iguais, maiores do que, maiores do que iguais | `Int`, `BigInt` ou `Double`
 `==`, `!=` | Binário | comparações iguais e não iguais | qualquer tipo primitivo
 `&&&` | Binário | Bitwise E | `Int` ou `BigInt`
 `^^^` | Binário | Bitwise XOR | `Int` ou `BigInt`
 <code>\|\|\|</code> | Binário | Bitwise OR | `Int` ou `BigInt`
 `and` | Binário | AND lógico | `Bool`
 `or` | Binário | OR lógico | `Bool`
 `..` | Binário/Ternário | Operador de gama | `Int`
 `?` `|` | Ternário | Condicional | `Bool` para o lado esquerdo
`w/` `<-` | Ternário | Cópia e atualização | Ver [expressões de cópia e atualização](#copy-and-update-expressions)

## <a name="next-steps"></a>Passos seguintes

Agora que pode trabalhar com expressões Q# em, passe para [Operações Q# e Funções](xref:microsoft.quantum.guide.operationsfunctions) para aprender a definir e chamar operações e funções.
