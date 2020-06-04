---
title: 'Expressãos tipo em Q #'
description: Entenda como especificar, referenciar e combinar constantes, variáveis, operadores, operações e funções como expressões em Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: c4b2cc0bed44ffdfb191ba522d6526959e7c6708
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327310"
---
# <a name="type-expressions-in-q"></a>Expressãos tipo em Q #

## <a name="numeric-expressions"></a>Expressões numéricas

Expressões numéricas são expressões do `Int` `BigInt` tipo, ou `Double` .
Ou seja, ou são números inteiros ou de pontos flutuantes.

`Int`literais em Q# são escritos simplesmente como uma sequência de dígitos.
Os inteiros hexadecimais e binários são suportados com um `0x` `0b` e prefixo, respectivamente.

`BigInt`literais em Q# são escritos com um rasto `l` ou `L` sufixo.
Os grandes inteiros hexadecimais são suportados com um prefixo "0x".
Assim, todas são utilizações válidas de `BigInt` literais:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`literais em Q# são números de ponto flutuante escritos usando dígitos decimais.
Podem ser escritos com um ponto decimal, `.` e/ou uma parte exponencial indicada com 'e' ou 'E' (após o qual apenas são válidos um possível sinal negativo e dígitos decimais).
Seguem-se `Double` literais válidos: `0.0` . . . `1.2e5` `1e-5` .

Dada a expressão de matriz de qualquer tipo de elemento, uma `Int` expressão pode ser formada utilizando a [`Length`](xref:microsoft.quantum.core.length) função incorporada, com a expressão de matriz em anexo em parênteses, `(` e `)` .
Por exemplo, se `a` está ligado a uma matriz, então é uma expressão `Length(a)` inteiro.
Se `b` for uma matriz de inteiros, `Int[][]` então é o número de `Length(b)` sub-matrizes em `b` , e é o número de `Length(b[1])` inteiros na segunda sub-matriz em `b` .

Tendo em conta duas expressões numéricas do mesmo tipo, os operadores `+` `-` `*` binários, e `/` podem ser usados para formar uma nova expressão numérica.
O tipo de nova expressão será o mesmo que os tipos de expressões constituintes.

Tendo em conta duas expressões mais recentes, o operador binário `^` (potência) pode ser utilizado para formar uma nova expressão de inteiro.
Da mesma forma, `^` pode ser usado com duas expressões duplas para formar uma nova expressão dupla.
Finalmente, `^` pode ser usado com um grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão de inteiro.
Neste caso, o segundo parâmetro deve encaixar em 32 bits; caso contrário, será levantado um erro de tempo de execução.

Tendo em conta duas expressões inteiros ou grandes, uma nova expressão inteiro ou grande inteiro pode ser formada utilizando os `%` operadores (modulus), `&&&` (bitwise E), `|||` (bitwise OR) ou `^^^` (bitwise XOR).

Dada a expressão de um inteiro ou de um grande inteiro à esquerda, e uma expressão inteiro à direita, os `<<<` operadores (mudança à esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão da esquerda.

O segundo parâmetro (a quantidade de turno) para uma operação por turnos deve ser superior ou igual a zero; o comportamento para quantidades de turno negativas é indefinido.
O valor de deslocação para qualquer operação por turnos também deve caber em 32 bits; caso contrário, será levantado um erro de tempo de execução.
Se o número a ser deslocado for um número inteiro, então o valor do turno é `mod 64` interpretado; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.

Tanto para os valores inteiros como para os grandes valores inteiros, as mudanças são aritmética.
Deslocar um valor negativo tanto à esquerda como à direita resultará num número negativo.
Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.

A divisão de inteiros e o módulo inteiro seguem o mesmo comportamento para números negativos como C#.
Ou seja, `a % b` terá sempre o mesmo sinal `a` que, e sempre será `b * (a / b) + a % b` `a` igual.
Por exemplo:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

A grande divisão de inteiros e o módulo funcionam da mesma forma.

Dada qualquer expressão numérica, uma nova expressão pode ser formada usando o `-` operador unary.
A nova expressão será do mesmo tipo que a expressão constituinte.

Dada qualquer expressão completa ou grande, pode formar-se uma nova expressão do mesmo tipo utilizando o `~~~` operador unary (pequeno complemento).

## <a name="boolean-expressions"></a>Expressões booleanas

Os dois `Bool` valores literais são `true` `false` e.

Tendo em conta duas expressões do mesmo tipo primitivo, os `==` `!=` operadores binários podem ser utilizados para construir uma `Bool` expressão.
A expressão será verdadeira se as duas expressões forem iguais, e falsas se não.

Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores desembrulhados podem ser comparados. Por exemplo, utilizando o operador "desembrulhar" `!` (explicado em pormenor nos [tipos em Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

A comparação entre igualdade de `Qubit` valores é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.
O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.

A comparação entre a igualdade e `Double` os valores pode ser enganosa devido aos efeitos de arredondamento.
Por exemplo, `49.0 * (1.0/49.0) != 1.0` . .

Tendo em conta duas expressões numéricas, os operadores binários `>` , e podem ser `<` `>=` `<=` usados para construir uma nova expressão booleana que é verdade se a primeira expressão for respectivamente maior do que, menos do que, maior ou igual a, ou inferior ou igual à segunda expressão.

Tendo em conta duas expressões booleanas, os `and` `or` operadores binários podem ser usados para construir uma nova expressão booleana que é verdade se ambas (resp. ou ambas) as duas expressões forem verdadeiras.

Dada qualquer expressão booleana, o `not` operador unary pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.

## <a name="string-expressions"></a>Expressões de cordas

Q# permite que as cordas sejam utilizadas na `fail` declaração (explicada no [Control Flow)](xref:microsoft.quantum.guide.controlflow#fail-statement)e na [`Message`](xref:microsoft.quantum.intrinsic.message) função padrão.
O comportamento específico deste último depende da utilização do simulador, mas normalmente escreve uma mensagem para a consola anfitriã quando é chamada durante um programa Q#.

As cordas em Q# são literais ou cordas interpoladas.

As letras de corda são semelhantes às simples cordas literais na maioria das línguas: uma sequência de caracteres Unicode incluídos em citações duplas, `"` .
Dentro de uma corda, o personagem de barra traseira `\` pode ser usado para escapar de um personagem de dupla citação, e para inserir uma nova linha como , um retorno de `\n` carruagem como , e uma guia `\r` como `\t` .
Por exemplo:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Cordas interpoladas

A sintaxe Q# para interpolações de cordas é um subconjunto da sintaxe C#, mas resumimos aqui os pontos-chave que dizem respeito a Q#.
As principais distinções são discutidas abaixo.

Para identificar uma corda literal como uma corda interpolada, prepare-a com o `$` símbolo.
Não se pode ter nenhum espaço em branco entre o `$` e o que começa uma corda `"` literal.

O seguinte é um exemplo básico usando a [`Message`](xref:microsoft.quantum.intrinsic.message) função para escrever o resultado de uma medição para a consola, ao lado de outras expressões Q#.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Qualquer expressão Q# válida pode aparecer numa corda interpolada.

Mais detalhes sobre a sintaxe C# podem ser encontrados em [*Cordas Interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).
A distinção mais notável é que Q# não suporta cordas interpoladas verbatim (multi-line).
Expressões dentro de uma corda interpolada seguem a sintaxe Q#, não a sintaxe C#.

## <a name="range-expressions"></a>Expressões de alcance

Tendo em conta as três `Int` expressões `start` , e , é uma expressão de alcance cujo primeiro elemento é , o segundo `step` elemento é , o terceiro elemento é , `stop` `start .. step .. stop` `start` `start+step` `start+step+step` etc., até `stop` ser passado.
Um intervalo pode estar vazio se, por exemplo, `step` for positivo e `stop < start` .
O último elemento da gama será `stop` se a diferença entre e é um `start` `stop` múltiplo integral `step` de; ou seja, a gama é inclusiva em ambas as extremidades.

Tendo em conta `Int` duas expressões `start` `stop` e, `start .. stop` é uma expressão de alcance que é igual a `start .. 1 .. stop` .
Note que o implícito `step` é +1 mesmo que `stop` seja `start` inferior; em tal caso, o intervalo está vazio.

Algumas gamas de exemplos são:

- `1..3`é o alcance 1, 2, 3.
- `2..2..5`é o alcance 2, 4.
- `2..2..6`é o alcance 2, 4, 6.
- `6..-2..2`é o alcance 6, 4, 2.
- `2..1`é o alcance vazio.
- `2..6..7`é o alcance 2.
- `2..2..1`é o alcance vazio.
- `1..-1..2`é o alcance vazio.

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

Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas `(` e `)` .
Por exemplo, `(1, One)` é uma `(Int, Result)` expressão.

Além das literais, as únicas expressões de tuple são símbolos que são obrigados a tuple valores, elementos de matrizes de tuple, e invocações callable que devolvem tuples.

## <a name="user-defined-type-expressions"></a>Expressões de tipo definido pelo utilizador

Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.
Por exemplo, se `IntPair` for um tipo definido pelo utilizador baseado em , `(Int, Int)` então seria um literal válido desse `IntPair(2, 3)` tipo.

Além das literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos de matrizes desse tipo, e invocações pôveis que devolvem esse tipo.

## <a name="unwrap-expressions"></a>Desembrulhar expressões

Em Q#, o operador de desembrulhar é um ponto de exclamação em fuga `!` .
Por exemplo, se `IntPair` for um tipo definido pelo utilizador com tipo `(Int, Int)` subjacente, e fosse uma `s` variável com `IntPair(2, 3)` valor, então `s!` seria `(2, 3)` .

Para os tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador. o operador de desembrulhar pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s` .
Assim, se `WrappedPair` for um tipo definido pelo utilizador com tipo `IntPair` subjacente, e é uma `t` variável com `WrappedPair(IntPair(1,2))` valor, então `t!!` seria `(1,2)` .

O `!` operador tem uma precedência mais elevada do que todos os outros operadores que não para a `[]` indexação e corte de matrizes.
`!`e `[]` ligar posicionalmente; ou seja, `a[i]![3]` deve ser lido como : pegue no `((a[i])!)[3]` `i` 'th elemento de `a` , desembrulhá-lo, e, em seguida, obter o terceiro elemento do valor desembrulhado (que deve ser uma matriz).

A precedência do `!` operador tem um impacto que pode não ser óbvio.
Se uma função ou operação devolver um valor que seja desembrulhado, a função ou chamada de funcionamento deve ser fechada em parênteses para que o argumento se ligue à chamada e não ao desembrulho.
Por exemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expressões de matriz

Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas `[` e `]` .
Todos os elementos devem ser compatíveis com o mesmo tipo.

Tendo em conta duas matrizes do mesmo tipo, o operador binário `+` pode ser utilizado para formar uma nova matriz que é a concatenação das duas matrizes.
Por exemplo, `[1,2,3] + [4,5,6]` é `[1,2,3,4,5,6]` .

### <a name="array-creation"></a>Criação de Matrizes

Dado um tipo e uma `Int` expressão, o `new` operador pode ser utilizado para alocar uma nova matriz do tamanho dado.
Por exemplo, `new Int[i + 1]` atribuiria uma nova `Int` matriz com `i + 1` elementos.

Não são permitidos literais de matrizes `[]` vazias.
Em vez disso, a utilização `new ★[0]` , onde é reservado para um tipo `★` adequado, permite criar a matriz de comprimento zero desejada.

Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.
Na maioria dos casos, esta é uma variação de zero.

Para qubits e callables, que são referências a entidades, não existe um valor padrão razoável.
Assim, para estes tipos, o padrão é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.
Isto é semelhante a uma referência nula em línguas como C# ou Java.
Os conjuntos que contenham qubits ou calcáveis devem ser corretamente inicializados com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança. As rotinas de inicialização adequadas podem ser encontradas em <xref:microsoft.quantum.arrays> .

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
 `Range` | A gama vazia,`1..1..0`
 `Callable` | _inválido callable_
 `Array['T]` | `'T[0]`

Os tipos de tuple são elemento-por-elemento inicializados.


### <a name="array-elements"></a>Elementos de matriz

Dada a expressão de matriz e uma `Int` expressão, uma nova expressão pode ser formada usando o operador de `[` elementos de matriz e `]` matriz.
A nova expressão será do mesmo tipo que o tipo de elemento da matriz.
Por exemplo, se `a` está ligado a uma matriz de `Double` s, então `a[4]` é uma `Double` expressão.

Se a expressão da matriz não for um identificador simples, deve ser fechada em parênteses para selecionar um elemento.
Por exemplo, se `a` e `b` forem ambos conjuntos de `Int` s, um elemento da concatenação seria expresso como:

```qsharp
(a + b)[13]
```

Todos os arrays em Q# são baseados em zero.
Ou seja, o primeiro elemento de uma matriz `a` é `a[0]` sempre.


### <a name="array-slices"></a>Fatias de Matriz

Dada a expressão de matriz e uma `Range` expressão, uma nova expressão pode ser formada usando o operador de `[` fatias de `]` matriz e matriz.
A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range` , na ordem definida pelo `Range` .
Por exemplo, se `a` estiver ligado a um conjunto de `Double` s, então `a[3..-1..0]` é uma expressão que contém os `Double[]` primeiros quatro elementos de `a` mas na ordem inversa como aparecem em `a` .

Se a `Range` fatia estiver vazia, a fatia de matriz resultante terá um comprimento zero.

Tal como acontece com os elementos de matriz de referência, se a expressão da matriz não for um simples identificador, deve ser fechada parênteses para cortar.
Se `a` e forem ambos `b` conjuntos de `Int` s, uma fatia da concatenação seria expressa como:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valores inferidos de início/fim

Começando com o nosso lançamento 0.8, apoiamos expressões contextuais para corte de alcance. Em especial, os valores de arranque e de fim de gama podem ser omitidos no contexto de uma expressão de corte de gama. Nesse caso, o compilador aplicará as seguintes regras para inferir os delimiters previstos para o intervalo. 

Por exemplo, se o valor inicial da gama for omitido, então o valor inicial inferido 
- é zero se nenhum passo for especificado ou o passo especificado é positivo, e 
- é o comprimento da matriz fatiada menos um se o passo especificado for negativo. 

Se o valor final da gama for omitido, então o valor final inferido 
- é o comprimento da matriz fatiada menos um se nenhum passo for especificado ou o passo especificado é positivo, e 
- é zero se o passo especificado for negativo. 

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

Uma vez que todos os tipos Q# são tipos de valor — com os qubits a assumirem um papel um pouco especial — formalmente é criada uma "cópia" quando um valor está ligado a um símbolo, ou quando um símbolo é recuperado. Ou seja, o comportamento de Q# é o mesmo que se uma cópia fosse criada numa missão.
Naturalmente, na prática, apenas as peças relevantes são recriadas conforme necessário. 

Isto inclui também matrizes.
Em particular, não é possível atualizar os itens de matriz. Modificar uma matriz existente requer uma alavancagem de um mecanismo *de cópia e atualização.*

Novas matrizes podem ser criadas a partir das existentes através de expressões *de cópia e atualização.*
Uma expressão de cópia e atualização é uma expressão do `expression1 w/ expression2 <- expression3` formulário, onde `expression1` tem de ser do tipo para algum tipo `T[]` `T` .
O segundo `expression2` define os índices dos elementos(s) para modificar em comparação com a matriz `expression1` e tem de ser de tipo ou de tipo `Int` `Range` .
Se `expression2` for do `Int` tipo, tem de ser do `expression3` `T` tipo. Se `expression2` for do `Range` tipo, tem de ser do `expression3` `T[]` tipo.

Uma expressão de cópia e atualização `arr w/ idx <- value` constrói uma nova matriz com todos os elementos definidos para o elemento correspondente em , exceto os `arr` elementos em , que são `idx` definidos para o(s) em `value` . Por exemplo, se `arr` contiver uma `[0,1,2,3]` matriz, então 
- `arr w/ 0 <- 10`é a matriz `[10,1,2,3]` .
- `arr w/ 2 <- 10`é a matriz `[0,1,10,3]` .
- `arr w/ 0..2..3 <- [10,12]`é a matriz `[10,1,12,3]` .

#### <a name="copy-and-update-expressions-for-named-items"></a>Expressões de cópia e atualização para itens nomeados

Expressões semelhantes existem para itens nomeados em tipos definidos pelo utilizador. 

Considere, por exemplo, o tipo 

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

Note que mais detalhes sobre tipos de chamadas podem ser encontrados abaixo, bem como na página seguinte, [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions).

Se o tipo de elemento comum for um tipo de funcionamento ou função, todos os elementos devem ter os mesmos tipos de entrada e saída.
O tipo de elemento da matriz irá suportar quaisquer funtores que sejam suportados por todos os elementos.
Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:

- `[Op1, Op2]`é uma série de `(Qubit[] => Unit)` operações.
- `[Op1, Op3]`é uma série de `(Qubit[] => Unit is Adj)` operações.
- `[Op2, Op3]`é uma série de `(Qubit[] => Unit is Ctl)` operações.

No entanto, embora `(Qubit[] => Unit is Adj)` as `(Qubit[] => Unit is Ctl)` operações tenham o tipo de base comum `(Qubit[] => Unit)` de, note-se que as matrizes destes operadores não partilham um tipo de base comum. *of* Por exemplo, `[[Op1], [Op2]]` atualmente levantaria um erro porque está a tentar criar uma matriz dos tipos de matrizes incompatíveis `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .


## <a name="conditional-expressions"></a>Expressões Condicionais

Tendo em conta duas outras expressões do mesmo tipo e uma expressão booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação `?` e a barra vertical `|` .
Por exemplo, `a==b ? c | d` . .
Neste exemplo, o valor da expressão condicional será `c` se for verdade e se for `a==b` `d` falso.

### <a name="conditional-expressions-with-callables"></a>Expressões condicionais com callables

As duas expressões podem avaliar operações que tenham as mesmas entradas e saídas, mas suportam diferentes functors.
Neste caso, o tipo de expressão condicional é uma operação com as entradas e saídas que suportam quaisquer funtores apoiados por ambas as expressões.
Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:

- `flag ? Op1 | Op2`é uma `(Qubit[] => Unit)` operação.
- `flag ? Op1 | Op3`é uma `(Qubit[] => Unit is Adj)` operação.
- `flag ? Op2 | Op3`é uma `(Qubit[] => Unit is Ctl)` operação.

Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de funcionamento, essa chamada só será efetuada se esse resultado for o valor da chamada.
Por exemplo, no caso `a==b ? C(qs) | D(qs)` , se `a==b` for verdade, a `C` operação será invocada, e se for falsa, só `D` será invocada.
Isto é semelhante ao curto-circuito em outras línguas.

## <a name="callable-expressions"></a>Expressões calláveis

Um literal chamado é o nome de uma operação ou função definida no âmbito de compilação.
Por exemplo, `X` é uma operação literal que se refere à operação padrão da `X` biblioteca, e é uma `Message` função literal que se refere à função de biblioteca `Message` padrão.

Se uma operação suporta o `Adjoint` functor, então `Adjoint op` é uma expressão de operação.
Da mesma forma, se a operação suporta o `Controlled` functor, então `Controlled op` é uma expressão de operação.
Os tipos destas expressões são especificados nas [especializações da operação Call](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).

Os functores `Adjoint` (e `Controlled` ) ligam-se mais estreitamente do que todos os outros operadores, com exceção do operador de desembrulhar `!` e da indexação da matriz com []».
Assim, todos são legais, assumindo que as operações suportam os funtores utilizados:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Expressões de caloisos por tipo parametrizadas

Um literal chamado pode ser usado como um valor, por exemplo, para atribuir a uma variável ou para passar para outra chamada.
Neste caso, se a chamada tiver [parâmetros de tipo,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)devem ser fornecidos como parte do valor de chamada.
Um valor calável não pode ter parâmetros de tipo não especificados.

Por exemplo, se `Fun` for uma função com `'T1->Unit` assinatura:

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expressões de invocação callable

Dada uma expressão callable (operação ou função) e uma expressão tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada por anexar a expressão de tuple à expressão callable.
O tipo de expressão de invocação é o tipo de saída da assinatura do callable.

Por exemplo, se `Op` for uma operação com `((Int, Qubit) => Double)` assinatura, é uma expressão do tipo `Op(3, qubit1)` `Double` .
Da mesma forma, se `Sin` for uma função com `(Double -> Double)` assinatura, é uma expressão do tipo `Sin(0.1)` `Double` .
Finalmente, se `Builder` é uma função com `(Int -> (Int -> Int))` assinatura, então `Builder(3)` é uma função de Into to Int.

Invocar o resultado de uma expressão de valor callable requer um par extra de parênteses em torno da expressão callable.
Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:

```qsharp
(Builder(3))(2)
```

Ao invocar uma chamada [tipo-parametrizada,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) os parâmetros do tipo real podem ser especificados dentro dos suportes angulares `<` e após a expressão `>` callable.
Isto é geralmente desnecessário, uma vez que o compilador Q# infere os tipos reais.
No entanto, *é* necessário para [a aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se um argumento porontose de tipo não for especificado.
Também é por vezes útil ao passar operações com diferentes suportes de functor para um callable.

Por exemplo, se `Func` tiver assinatura , e ter assinatura , e tiver assinatura , para invocar `('T1, 'T2, 'T1) -> 'T2` como primeiro `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` `Op1` argumento, como o `Op2` segundo, e como o `Op3` terceiro:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A especificação do tipo é necessária porque `Op3` e `Op1` tem diferentes tipos, de modo que o compilador tratará isto como ambíguo sem a especificação.


## <a name="operator-precedence"></a>Precedência do operador

Todos os operadores binários são associados à direita, `^` exceto.

Os suportes `[` `]` e, para cortar e indexar a matriz, ligam-se perante qualquer operador.

Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.

Os parênteses para a invocação de funcionamento e função também se ligam perante qualquer operador, mas após a indexação de matrizes e funtores.

Operadores por ordem de precedência, da mais alta para a mais baixa:

Operador | Arity | Description | Tipos operand
---------|----------|---------|---------------
 trailing`!` | Unária | Desembrulhar | Qualquer tipo definido pelo utilizador
 `-`, `~~~`, `not` | Unária | Numérico negativo, complemento bitwise, negação lógica | `Int`, `BigInt` ou `Double` `-` para, ou para `Int` `BigInt` `~~~` , `Bool``not`
 `^` | Binário | Poder inteiro | `Int`ou `BigInt` para a base, para o `Int` expoente
 `/`, `*`, `%` | Binário | Divisão, multiplicação, módulo inteiro | `Int`, `BigInt` ou `Double` para `/` `*` e, ou `Int` `BigInt` para`%`
 `+`, `-` | Binário | Adição ou cadeia e concatenação de matriz, subtração | `Int`, `BigInt` ou `Double` , adicionalmente ou qualquer tipo de matriz `String` para`+`
 `<<<`, `>>>` | Binário | Turno da esquerda, turno da direita | `Int` ou `BigInt`
 `<`, `<=`, `>`, `>=` | Binário | Comparações menos do que, menos ou iguais, maiores do que, maiores do que iguais | `Int`, `BigInt` ou`Double`
 `==`, `!=` | Binário | comparações iguais e não iguais | qualquer tipo primitivo
 `&&&` | Binário | Bitwise E | `Int` ou `BigInt`
 `^^^` | Binário | Bitwise XOR | `Int` ou `BigInt`
 <code>\|\|\|</code> | Binário | Bitwise OR | `Int` ou `BigInt`
 `and` | Binário | AND lógico | `Bool`
 `or` | Binário | OR lógico | `Bool`
 `..` | Binário/Ternário | Operador de gama | `Int`
 `?` `|` | Ternário | Condicional | `Bool`para o lado esquerdo
`w/` `<-` | Ternário | Cópia e atualização | ver [expressões de cópia e atualização](#copy-and-update-expressions)

## <a name="next-steps"></a>Próximos passos

Agora que pode trabalhar com expressões em Q#, pode dirigir-se a [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions) para aprender a definir e chamar operações e funções.
