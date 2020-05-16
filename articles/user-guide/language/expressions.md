---
title: 'Tipo expressões em Q #'
description: Compreenda como especificar, referenciar e combinar constantes, variáveis, operadores, operações e funções como expressões em Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 93432cef9711b6780192cd59e92b09647a264b5c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431211"
---
# <a name="type-expressions-in-q"></a>Tipo expressões em Q #

## <a name="numeric-expressions"></a>Expressões numéricas

Expressões numéricas são expressões de `Int` `BigInt` tipo, ou `Double` .
Ou são números inteiros ou flutuantes.

`Int`os literais em Q# são escritos simplesmente como uma sequência de dígitos.
Os inteiros hexadecimais e binários são suportados com um `0x` `0b` prefixo, respectivamente.

`BigInt`os literais em Q# são escritos com um rasto `l` ou `L` sufixo.
Os grandes inteiros hexadecimais são suportados com um prefixo "0x".
Assim, todos os seguintes são usos válidos de `BigInt` literais:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`os literais em Q# são números de ponto flutuante escritos usando dígitos decimais.
Podem ser escritas com um ponto decimal, `.` e/ou uma parte exponencial indicada com 'e' ou 'E' (após o qual apenas um possível sinal negativo e dígitos decimais são válidos).
Seguem-se `Double` os literais válidos: `0.0` . `1.2e5` . `1e-5`

Dada a expressão da matriz de qualquer tipo de elemento, pode ser formada uma `Int` expressão utilizando a [`Length`](xref:microsoft.quantum.core.length) função incorporada, com a expressão da matriz fechada em parênteses, `(` e `)` .
Por exemplo, se `a` está ligado a uma matriz, então é uma expressão `Length(a)` inteiro.
Se `b` for um conjunto de conjuntos de inteiros, `Int[][]` então é o número de `Length(b)` sub-arrays em `b` , e é o número de `Length(b[1])` inteiros na segunda sub-matriz em `b` .

Tendo em conta duas expressões numéricas do mesmo tipo, os operadores `+` binários, e podem ser `-` `*` `/` usados para formar uma nova expressão numérica.
O tipo da nova expressão será o mesmo que os tipos das expressões constituintes.

Tendo em conta duas expressões inteiros, o operador binário `^` (potência) pode ser utilizado para formar uma nova expressão inteiro.
Da mesma forma, `^` pode ser usado com duas expressões duplas para formar uma nova expressão dupla.
Finalmente, `^` pode ser usado com uma grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão inteiro.
Neste caso, o segundo parâmetro deve caber em 32 bits; se não, um erro de tempo de execução será levantado.

Tendo em conta duas expressões inteiros ou grandes inteiros, uma nova expressão inteiro ou grande inteiro pode ser formada usando os `%` operadores (modulo), `&&&` (bitwise And), `|||` (bitwise OR), ou `^^^` (bitwise XOR).

Dado um inteiro ou uma expressão inteiro à esquerda, e uma expressão inteiro à direita, os `<<<` operadores (mudança de esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão esquerda.

O segundo parâmetro (o valor de deslocação) para uma das operações por turnos deve ser maior ou igual a zero; o comportamento para quantidades de mudança negativa é indefinido.
O montante de deslocação para qualquer uma das operações por turnos também deve caber em 32 bits; se não, um erro de tempo de execução será levantado.
Se o número a deslocar for um inteiro, então o valor do turno é `mod 64` interpretado; ou seja, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.

Tanto para valores inteiros como para grandes valores inteiros, as mudanças são aritméticas.
Mudar um valor negativo, quer à esquerda quer à direita, resultará num número negativo.
Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.

Divisão integer e modulo inteiro seguem o mesmo comportamento para números negativos que C#.
Ou seja, `a % b` terá sempre o mesmo sinal que , e sempre será igual `a` `b * (a / b) + a % b` `a` .
Por exemplo:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

A grande divisão de inteiros e o modulo funcionam da mesma forma.

Dada qualquer expressão numérica, pode ser formada uma nova expressão utilizando o `-` operador não-eléctrico.
A nova expressão será do mesmo tipo que a expressão constituinte.

Dada a expressão inteiro ou grande inteiro, pode formar-se uma nova expressão do mesmo tipo utilizando o `~~~` (complemento bitwise) do operador não-secundário.

## <a name="boolean-expressions"></a>Expressões booleanas

Os dois `Bool` valores literais são `true` `false` e.

Dadas duas expressões do mesmo tipo primitivo, os `==` operadores binários e `!=` binários podem ser utilizados para construir uma `Bool` expressão.
A expressão será verdadeira se as duas expressões forem iguais, e falsas se não forem.

Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores não embrulhados podem ser comparados. Por exemplo, utilizando o operador "desembrulhar" `!` (explicado em detalhe nos [Tipos em Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

A comparação da igualdade de `Qubit` valores é a igualdade de identidade; ou seja, se as duas expressões identificam o mesmo qubit.
O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.

A comparação da igualdade de `Double` valores pode ser enganosa devido aos efeitos arredondamentos.
Por exemplo, `49.0 * (1.0/49.0) != 1.0` .

Tendo em conta duas expressões numéricas, os operadores `>` binários, e podem ser `<` `>=` `<=` utilizados para construir uma nova expressão booleana que seja verdadeira se a primeira expressão for respectivamente maior do que, inferior ou igual, ou inferior ou igual ou igual à segunda expressão.

Dadas duas expressões booleanas, os `and` operadores e `or` binários podem ser usados para construir uma nova expressão booleana que é verdade se ambos (resp. ou ambos) as duas expressões forem verdadeiras.

Dada qualquer expressão booleana, o `not` operador não-secundário pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.

## <a name="string-expressions"></a>Expressões de cordas

Q# permite que as cordas sejam utilizadas na `fail` declaração (explicada no [Control Flow)](xref:microsoft.quantum.guide.controlflow#fail-statement)e na [`Message`](xref:microsoft.quantum.intrinsic.message) função padrão.
O comportamento específico deste último depende da aplicação do simulador, mas normalmente escreve uma mensagem para a consola anfitriã quando chamada durante um programa Q#.

As cordas em Q# são literais ou cordas interpoladas.

Os literais de cordas são semelhantes aos simples literais de cordas na maioria das línguas: uma sequência de caracteres Unicode fechados em citações duplas, `"` .
Dentro de uma corda, o personagem de corte traseiro pode ser usado para escapar a um personagem de `\` citação dupla, e para inserir uma nova linha como , um retorno de `\n` carruagem como , e um `\r` separador como `\t` .
Por exemplo:

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>Cordas interpoladas

A sintaxe Q# para interpolações de cordas é um subconjunto da sintaxe C#, mas resumemos aqui os pontos-chave como eles dizem respeito a Q#.
As principais distinções são discutidas abaixo.

Para identificar uma corda literal como uma corda interpolada, prepare-a com o `$` símbolo.
Não se pode ter espaço branco entre o `$` e o que começa uma corda `"` literal.

Segue-se um exemplo básico utilizando a [`Message`](xref:microsoft.quantum.intrinsic.message) função para escrever o resultado de uma medição para a consola, ao lado de outras expressões Q#.

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
Qualquer expressão Q# válida pode aparecer numa corda interpolada.

Mais detalhes sobre a sintaxe C# podem ser encontrados em [*Strings Interpolated*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).
A distinção mais notável é que Q# não suporta cordas interpoladas verbatim (multi-linhas).
Expressões dentro de uma corda interpolada seguem Q# sintaxe, não C# sintaxe.

## <a name="range-expressions"></a>Expressões de alcance

Dadas as três `Int` expressões, e é uma expressão de alcance cujo primeiro elemento é , o segundo elemento é , o `start` terceiro elemento é , `step` `stop` `start .. step .. stop` `start` `start+step` `start+step+step` etc., até `stop` que seja passado.
Uma gama pode estar vazia se, por exemplo, `step` for positiva e `stop < start` .
O último elemento da gama será `stop` se a diferença entre e é um `start` `stop` múltiplo integral `step` de; ou seja, a gama é inclusiva em ambas as extremidades.

Dadas duas `Int` expressões `start` `stop` e, `start .. stop` é uma expressão de alcance que é igual a `start .. 1 .. stop` .
Note que o implícito `step` é +1 mesmo que `stop` seja inferior `start` a; neste caso, o intervalo está vazio.

Algumas gamas de exemplo são:

- `1..3`é o intervalo 1, 2, 3.
- `2..2..5`é o intervalo 2, 4.
- `2..2..6`é o intervalo 2, 4, 6.
- `6..-2..2`é o alcance 6, 4, 2.
- `2..1`é o alcance vazio.
- `2..6..7`é o intervalo 2.
- `2..2..1`é o alcance vazio.
- `1..-1..2`é o alcance vazio.

## <a name="qubit-expressions"></a>Expressões Qubit

As `Qubit` únicas expressões são símbolos que estão ligados a `Qubit` valores ou elementos matrizes de `Qubit` matrizes.
Não há `Qubit` literal.

## <a name="pauli-expressions"></a>Expressões Pauli

Os quatro `Pauli` valores, `PauliI` `PauliX` `PauliY` `PauliZ` e, são todas `Pauli` expressões válidas.

Além disso, as `Pauli` únicas expressões são símbolos que estão ligados a `Pauli` valores ou elementos matrizes de `Pauli` matrizes.

## <a name="result-expressions"></a>Expressões de Resultados

Os dois `Result` valores, `One` `Zero` e, são `Result` expressões válidas.

Além disso, as `Result` únicas expressões são símbolos que estão ligados a `Result` valores ou elementos matrizes de `Result` matrizes.
Em particular, note que não é o mesmo que `One` o inteiro , e não há conversão direta entre `1` eles.
O mesmo se aplica a `Zero` `0` e.

## <a name="tuple-expressions"></a>Expressões tuple

Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas `(` e `)` .
Por exemplo, `(1, One)` é uma `(Int, Result)` expressão.

Além dos literais, as únicas expressões de tuple são símbolos que estão ligados a valores de tuple, elementos marray de matrizes de tuple, e invocações calíveis que devolvem tuples.

## <a name="user-defined-type-expressions"></a>Expressões de tipo definidas pelo utilizador

Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.
Por exemplo, se `IntPair` for um tipo definido pelo utilizador com base, `(Int, Int)` então seria um literal válido desse `IntPair(2, 3)` tipo.

Para além dos literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos manuais de matrizes desse tipo, e invocações calíveis que devolvem esse tipo.

## <a name="unwrap-expressions"></a>Desembrulhar Expressões

Em Q#, o operador de desembrulhar é um ponto de exclamação de trailing `!` .
Por exemplo, se `IntPair` for um tipo definido pelo utilizador com tipo `(Int, Int)` subjacente, e fosse uma `s` variável com `IntPair(2, 3)` valor, então `s!` seria `(2, 3)` .

Para tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador. O operador de desembrulhar pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s` .
Assim, se `WrappedPair` for um tipo definido pelo utilizador com tipo `IntPair` subjacente, e for uma `t` variável com `WrappedPair(IntPair(1,2))` valor, então `t!!` seria `(1,2)` .

O operador tem uma precedência maior do que todos os outros operadores que não o índice de `!` `[]` matriz e o corte.
`!`e `[]` ligar posicionalmente; isto é, `a[i]![3]` deve ser lido como : pegue o `((a[i])!)[3]` `i` 'th elemento de , `a` desembrulhe-o, e, em seguida, obtenha o 3º elemento do valor desembrulhado (que deve ser uma matriz).

A precedência do `!` operador tem um impacto que pode não ser óbvio.
Se uma função ou operação devolver um valor que depois seja desembrulhado, a função ou chamada de operação deve ser encerrada em parênteses de modo a que o argumento se ligue à chamada e não ao desembrulhar.
Por exemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expressões de matriz

Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas `[` e `]` .
Todos os elementos devem ser compatíveis com o mesmo tipo.


Tendo em conta duas matrizes do mesmo tipo, o operador binário `+` pode ser usado para formar uma nova matriz que é a concatenação das duas matrizes.
Por exemplo, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]` é.

### <a name="array-creation"></a>Criação de Matriz

Dado um tipo e uma `Int` expressão, o `new` operador pode ser utilizado para alocar um novo conjunto do tamanho dado.
Por exemplo, `new Int[i + 1]` atribuiria uma nova `Int` matriz com `i + 1` elementos.

Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.
Na maioria dos casos, esta é uma variação de zero.

Para qubits e callables, que são referências a entidades, não existe um valor razoável por defeito.
Assim, para estes tipos, a predefinição é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.
Isto é semelhante a uma referência nula em línguas como C# ou Java.
As matrizes que contenham qubits ou callables devem ser corretamente inicializadas com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança. Podem ser encontradas rotinas de inicialização adequadas em <xref:microsoft.quantum.arrays> .

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
 `Range` | O alcance vazio,`1..1..0`
 `Callable` | _inválido callable_
 `Array['T]` | `'T[0]`

Os tipos tuple são inicializados elemento a elemento.


### <a name="array-elements"></a>Elementos de matriz

Dada a expressão da matriz e uma `Int` expressão, pode formar-se uma nova expressão utilizando o operador de `[` elementos de `]` matriz e matriz.
A nova expressão será do mesmo tipo que o tipo de elemento da matriz.
Por exemplo, se `a` está ligado a uma série de `Double` s, então `a[4]` é uma `Double` expressão.

Se a expressão da matriz não for um identificador simples, deve ser fechada em parênteses para selecionar um elemento.
Por exemplo, se `a` e `b` ambos forem conjuntos de `Int` s, um elemento da concatenação seria expresso como:

```qsharp
(a + b)[13]
```

Todas as matrizes em Q# são baseadas em zero.
Ou seja, o primeiro elemento de uma matriz `a` é `a[0]` sempre.


### <a name="array-slices"></a>Fatias de matriz

Dada a expressão da matriz e uma `Range` expressão, pode formar-se uma nova expressão utilizando o operador de `[` fatias de `]` matriz e matriz.
A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range` , na ordem definida pela `Range` .
Por exemplo, se `a` está ligado a uma série de `Double` s, então `a[3..-1..0]` é uma expressão que contém os `Double[]` primeiros quatro elementos de `a` mas na ordem inversa como eles aparecem em `a` .

Se a estiver `Range` vazia, então a fatia de matriz resultante será de zero comprimento.

Tal como acontece com elementos de matriz referenciais, se a expressão da matriz não for um simples identificador, deve ser fechada a parênteses para cortar.
Se `a` e ambos são `b` conjuntos de `Int` s, uma fatia da concatenação seria expressa como:

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>Valores inferidos de início/fim

A partir do nosso lançamento 0.8, apoiamos expressões contextuais para corte de alcance. Em particular, os valores de início e fim de gama podem ser omitidos no contexto de uma expressão de corte de gama. Nesse caso, o compilador aplicará as seguintes regras para inferir os delimitadores pretendidos para a gama. 

Por exemplo, se o valor de início de gama for omitido, então o valor de início inferido 
- é zero se nenhum passo for especificado ou o passo especificado é positivo, e 
- é o comprimento da matriz fatiada menos uma se o passo especificado for negativo. 

Se o valor final do intervalo for omitido, então o valor final inferido 
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

Uma vez que todos os tipos de Q# são tipos de valor — com os qubits a assumirem um papel um pouco especial — formalmente é criada uma "cópia" quando um valor está ligado a um símbolo, ou quando um símbolo é recuperado. Ou seja, o comportamento do Q# é o mesmo que se uma cópia fosse criada na atribuição.
É claro que, na prática, apenas as peças relevantes são recriadas, se necessário. 

Isto, em particular, também inclui matrizes.
Em particular, não é possível atualizar itens de matriz. Para modificar uma matriz existente requer alavancar um mecanismo *de cópia e atualização.*

Novas matrizes podem ser criadas a partir das existentes através de expressões *de cópia e atualização.*
Uma expressão de cópia e atualização é uma expressão do `expression1 w/ expression2 <- expression3` formulário, onde `expression1` tem de ser de tipo para algum tipo `T[]` `T` .
O segundo `expression2` define os índices dos elementos a modificar em comparação com a matriz `expression1` e tem de ser de tipo ou de tipo `Int` `Range` .
Se `expression2` for de `Int` tipo, tem de ser de `expression3` `T` tipo. Se `expression2` for de `Range` tipo, tem de ser de `expression3` `T[]` tipo.

Uma expressão de cópia e atualização `arr w/ idx <- value` constrói uma nova matriz com todos os elementos definidos para o elemento correspondente, `arr` com exceção dos elementos em , que `idx` estão definidos para os ou os em `value` . Por exemplo, se `arr` contiver uma `[0,1,2,3]` matriz, então 
- `arr w/ 0 <- 10`é a `[10,1,2,3]` matriz.
- `arr w/ 2 <- 10`é a `[0,1,10,3]` matriz.
- `arr w/ 0..2..3 <- [10,12]`é a `[10,1,12,3]` matriz.

#### <a name="copy-and-update-expressions-for-named-items"></a>Expressões de cópia e atualização para itens nomeados

Existem expressões semelhantes para itens nomeados em tipos definidos pelo utilizador. 

Considere, por exemplo, o tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Se `c` contiver o valor do `Complex(1., -1.)` tipo, `c w/ Re <- 0.` então é uma expressão de tipo `Complex` que avalia para `Complex(0., -1.)` .

### <a name="jagged-arrays"></a>Matrizes Irregulares

Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes.
Os elementos de uma matriz irregular podem ser de diferentes tamanhos.
O exemplo que se segue mostra como declarar e inicializar uma matriz irregular representando uma tabela de multiplicação.

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

Note que mais detalhes sobre tipos de callable podem ser encontrados abaixo, bem como na página seguinte, [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions).

Se o tipo de elemento comum for um tipo de funcionamento ou de função, todos os elementos devem ter os mesmos tipos de entrada e saída.
O tipo de elemento da matriz irá suportar todos os functors que sejam suportados por todos os elementos.
Por exemplo, se `Op1` , e todos são , mas apoia , apoia , `Op2` e apoia `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:

- `[Op1, Op2]`é uma série de `(Qubit[] => Unit)` operações.
- `[Op1, Op3]`é uma série de `(Qubit[] => Unit is Adj)` operações.
- `[Op2, Op3]`é uma série de `(Qubit[] => Unit is Ctl)` operações.

Não são permitidos os literais `[]` vazios.
Em vez disso, a `new ★[0]` utilização, onde é o espaço reservado para um tipo `★` adequado, permite criar a matriz de comprimento zero desejada.


## <a name="conditional-expressions"></a>Expressões Condicionais

Tendo em conta duas outras expressões do mesmo tipo e uma expressão booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação `?` e a barra vertical `|` .
Por exemplo, `a==b ? c | d` .
Neste exemplo, o valor da expressão condicional será `c` se for verdade e se for `a==b` `d` falso.

### <a name="conditional-expressions-with-callables"></a>Expressões condicionais com callables

As duas expressões podem avaliar para operações que tenham as mesmas inputs e saídas, mas suportam diferentes functores.
Neste caso, o tipo de expressão condicional é uma operação com as inputs e saídas que suporta todos os functors suportados por ambas as expressões.
Por exemplo, se `Op1` , e todos são , mas apoia , apoia , `Op2` e apoia `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:

- `flag ? Op1 | Op2`é uma `(Qubit[] => Unit)` operação.
- `flag ? Op1 | Op3`é uma `(Qubit[] => Unit is Adj)` operação.
- `flag ? Op2 | Op3`é uma `(Qubit[] => Unit is Ctl)` operação.

Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de operação, essa chamada só ocorrerá se esse resultado for o valor da chamada.
Por exemplo, no `a==b ? C(qs) | D(qs)` caso, se `a==b` for verdade, a operação será `C` invocada, e se for falsa, só `D` será invocada.
Isto é semelhante ao curto-circuito noutras línguas.

## <a name="callable-expressions"></a>Expressões Insensíveis

Um literal calivel é o nome de uma operação ou função definida no âmbito da compilação.
Por exemplo, `X` é uma operação literal que se refere à operação padrão da `X` biblioteca, e é uma `Message` função literal que se refere à função padrão da `Message` biblioteca.

Se uma operação suporta o `Adjoint` functor, `Adjoint op` então é uma expressão de operação.
Da mesma forma, se a operação suporta o `Controlled` functor, então é uma expressão de `Controlled op` operação.
Os tipos destas expressões são especificados nas [especializações](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)da operação Call .

Os functores `Adjoint` (e `Controlled` ) ligam-se mais estreitamente do que todos os outros operadores, com exceção do operador de desembrulhar e da indexação da `!` matriz com []».
Assim, todos os seguintes são legais, assumindo que as operações apoiam os functors utilizados:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>Expressões de callable parametrizadas tipo

Um literal calivel pode ser usado como um valor, por exemplo, atribuir a uma variável ou passar para outra chamada.
Neste caso, se o reponsado tiver parâmetros de [tipo,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)devem ser fornecidos como parte do valor calivel.
Um valor callable não pode ter nenhum tipo de parâmetros não especificados.

Por exemplo, se `Fun` for uma função com `'T1->Unit` assinatura:

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expressões de invocação callable

Dada uma expressão (operação ou função) insensível e uma expressão de tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada através da adesão da expressão de tuple à expressão calúgica.
O tipo de expressão de invocação é o tipo de saída da assinatura do callable.

Por exemplo, se `Op` for uma operação com `((Int, Qubit) => Double)` assinatura, é uma expressão de tipo `Op(3, qubit1)` `Double` .
Da mesma forma, se `Sin` for uma função com `(Double -> Double)` assinatura, é uma expressão de tipo `Sin(0.1)` `Double` .
Finalmente, se `Builder` é uma função com `(Int -> (Int -> Int))` assinatura, então `Builder(3)` é uma função de Into to Int.

Invocar o resultado de uma expressão de valor calivel requer um par extra de parênteses em torno da expressão caluniável.
Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:

```qsharp
(Builder(3))(2)
```

Ao invocar uma chamada de tipo [parametrizada,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) os parâmetros do tipo real podem ser especificados dentro dos suportes angulares `<` e após a expressão `>` caltável.
Isto é geralmente desnecessário, uma vez que o compilador Q# inferirá os tipos reais.
No entanto, *é* necessário para [aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se um argumento de tipo paramétrico for deixado não especificado.
Também é por vezes útil quando se passam operações com diferentes suportes de functor para um callable.

Por exemplo, se `Func` tiver assinatura , e tiver assinatura , e tiver assinatura , para invocar `('T1, 'T2, 'T1) -> 'T2` como primeiro `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` `Op1` argumento, como o `Op2` segundo, e como o `Op3` terceiro:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A especificação do tipo é necessária porque `Op3` e `Op1` tem tipos diferentes, por isso o compilador tratará isto como ambíguo sem a especificação.


## <a name="operator-precedence"></a>Precedência do operador

Todos os operadores binários são associativos de direito, exceto `^` .

Os suportes `[` `]` e, para cortar matrize e indexação, ligam-se perante qualquer operador.

Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.

Os parênteses para a exploração e a invocação de funções também se ligam perante qualquer operador, mas após a indexação da matriz e functores.

Operadores por ordem de precedência, dos mais elevados aos mais baixos:

Operador | Rio Arity | Descrição | Tipos de operand
---------|----------|---------|---------------
 arrastando`!` | Unary | Desembrulhar | Qualquer tipo definido pelo utilizador
 `-`, `~~~`, `not` | Unary | Negativa numérica, um complemento bitwise, negação lógica | `Int`, `BigInt` ou `Double` `-` para, ou `Int` `BigInt` `~~~` para, `Bool` para`not`
 `^` | Binário | Poder inteiro | `Int`ou `BigInt` para a base, para o `Int` expoente
 `/`, `*`, `%` | Binário | Divisão, multiplicação, modulo inteiro | `Int`, `BigInt` ou `Double` para `/` `*` e, ou `Int` `BigInt` para`%`
 `+`, `-` | Binário | Adição ou cadeia e concatenação de cordas, subtração | `Int`, `BigInt` `Double` ou, adicionalmente ou qualquer tipo de `String` matriz para`+`
 `<<<`, `>>>` | Binário | Turno da esquerda, turno da direita | `Int` ou `BigInt`
 `<`, `<=`, `>`, `>=` | Binário | Comparações menos ou iguais, mais do que iguais, maiores do que iguais ou iguais | `Int`, `BigInt` ou.`Double`
 `==`, `!=` | Binário | comparações iguais e não iguais | qualquer tipo primitivo
 `&&&` | Binário | Bitwise E | `Int` ou `BigInt`
 `^^^` | Binário | Bitwise XOR | `Int` ou `BigInt`
 <code>\|\|\|</code> | Binário | Bitwise OU | `Int` ou `BigInt`
 `and` | Binário | Lógico E | `Bool`
 `or` | Binário | Lógica OU | `Bool`
 `..` | Binário/Ternary | Operador de gama | `Int`
 `?` `|` | Ternário | Condicional | `Bool`para o lado esquerdo
`w/` `<-` | Ternário | Cópia e atualização | ver [expressões de cópia e atualização](#copy-and-update-expressions)

## <a name="whats-next"></a>O que se segue?
Agora que pode trabalhar com expressões em Q#, pode dirigir-se a [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions) para aprender a definir e chamar operações e funções.
