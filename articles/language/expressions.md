---
title: Q# Expressões
description: Compreenda como especificar, referenciar e combinar constantes, variáveis, operadores, operações e funções como expressões em Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: fbde873f220d737db17f889d00be33541e3eb59b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907414"
---
# <a name="expressions"></a>Expressões

## <a name="grouping"></a>Agrupamento

Dada qualquer expressão, essa mesma expressão em parênteses é uma expressão do mesmo tipo.
Por exemplo, `(7)` é uma expressão `Int`, `([1,2,3])` é uma expressão de tipo de matriz de `Int`s, e `((1,2))` é uma expressão com tipo `(Int, Int)`.

A equivalência entre valores simples e tuples de um único elemento descrito [no modelo](xref:microsoft.quantum.language.type-model#tuple-types) do tipo remove a ambiguidade entre `(6)` como um grupo e `(6)` como uma tuple de um único elemento.

## <a name="symbols"></a>Símbolos

O nome de um símbolo ligado ou atribuído a um valor de tipo `'T` é uma expressão de tipo `'T`.
Por exemplo, se o símbolo `count` está ligado ao valor inteiro `5`, então `count` é uma expressão inteiro.

## <a name="numeric-expressions"></a>Expressões numéricas

Expressões numéricas são expressões de tipo `Int`, `BigInt`ou `Double`.
Ou são números inteiros ou flutuantes.

`Int` literals em Q# são idênticos C#aos inteiros literais em , exceto que não é necessário seguir "l" ou "L" (ou permitido).
Os inteiros hexadecimais e binários são suportados com um prefixo "0x" e "0b", respectivamente.

`BigInt` os literais em Q# são idênticos às grandes cordas de inteiro em .NET, com um "l" ou "L".
Os grandes inteiros hexadecimais são suportados com um prefixo "0x".
Assim, todos os seguintes usos válidos de `BigInt` literais:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` literals em Q# são idênticos aos duplos literais em C#, exceto que não é necessário seguir "d" ou "D" (ou permitido).

Dada a expressão da matriz de qualquer tipo de elemento, pode formar-se uma expressão `Int` utilizando a função `Length` incorporada, com a expressão da matriz fechada em parênteses, `(` e `)`.
Por exemplo, se `a` está ligado a uma matriz, então `Length(a)` é uma expressão inteiro.
Se `b` é um conjunto de conjuntos de inteiros, `Int[][]`, então `Length(b)` é o número de sub-matrizes em `b`, e `Length(b[1])` é o número de inteiros na segunda sub-matriz em `b`.

Tendo em conta duas expressões numéricas do mesmo tipo, os operadores binários `+`, `-`, `*`e `/` podem ser usados para formar uma nova expressão numérica.
O tipo da nova expressão será o mesmo que os tipos das expressões constituintes.

Tendo em conta duas expressões inteiros, o operador binário `^` (potência) pode ser usado para formar uma nova expressão inteiro.
Da mesma forma, `^` pode ser usado com duas expressões duplas para formar uma nova expressão dupla.
Finalmente, `^` pode ser usado com um grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão inteiro.
Neste caso, o segundo parâmetro deve caber em 32 bits; se não, um erro de tempo de execução será levantado.

Tendo em conta duas expressões inteiros ou grandes inteiros, uma nova expressão inteiro ou grande inteiro pode ser formada usando os operadores `%` (modulo), `&&&` (bitwise And), `|||` (bitwise OR) ou `^^^` (bitwise XOR).

Dado um inteiro ou uma expressão inteiro à esquerda, e uma expressão inteiro à direita, os operadores `<<<` (turno da esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão esquerda.

O segundo parâmetro (o valor de deslocação) para uma das operações por turnos deve ser maior ou igual a zero; o comportamento para quantidades de mudança negativa é indefinido.
O montante de deslocação para qualquer uma das operações por turnos também deve caber em 32 bits; se não, um erro de tempo de execução será levantado.
Se o número a deslocar for um inteiro, então o valor do turno é interpretado `mod 64`; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.

Tanto para valores inteiros como para grandes valores inteiros, as mudanças são aritméticas.
Mudar um valor negativo, quer à esquerda quer à direita, resultará num número negativo.
Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.

Divisão integer e modulo inteiro seguem o C#mesmo comportamento para números negativos que .
Ou seja, `a % b` terá sempre o mesmo sinal que `a`, e `b * (a / b) + a % b` será sempre igual a `a`.
Por exemplo:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

A grande divisão de inteiros e o modulo funcionam da mesma forma.

Dada qualquer expressão numérica, pode ser formada uma nova expressão utilizando o operador `-` não-secundário.
A nova expressão será do mesmo tipo que a expressão constituinte.

Dada a expressão inteiro ou grande inteiro, pode formar-se uma nova expressão do mesmo tipo utilizando o operador `~~~` (complemento bitwise).

## <a name="boolean-expressions"></a>Expressões booleanas

Os dois valores `Bool` literários são `true` e `false`.

Dadas duas expressões do mesmo tipo primitivo, os operadores `==` e `!=` binários podem ser utilizados para construir uma expressão `Bool`.
A expressão será verdadeira se as duas expressões forem iguais, e falsas se não forem.

Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores não embrulhados podem ser comparados. Por exemplo, utilizando o operador "desembrulhar" `!` (explicado na página do [modelo do tipo Q#](xref:microsoft.quantum.language.type-model#user-defined-types)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

A comparação da igualdade entre valores `Qubit` é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.
O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.

A comparação da igualdade entre valores `Double` pode ser enganosa devido aos efeitos arredondamentos.
Por exemplo, `49.0 * (1.0/49.0) != 1.0`.

Tendo em conta duas expressões numéricas, os operadores binários `>`, `<`, `>=`e `<=` podem ser usados para construir uma nova expressão booleana que seja verdade se a primeira expressão for respectivamente maior do que, inferior ou igual, ou inferior ou igual à segunda expressão.

Dadas duas expressões booleanas, os operadores binários `and` e `or` podem ser usados para construir uma nova expressão booleana que é verdade se ambos (resp. ou ambos) as duas expressões forem verdadeiras.

Dada qualquer expressão booleana, o `not` operador não-secundário pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.

## <a name="string-expressions"></a>Expressões de cordas

Q# permite que as cordas sejam usadas na declaração `fail` e na função padrão `Log`.

As cordas em Q# são literais ou cordas interpoladas.
Os literais de cordas são semelhantes aos simples literais de cordas na maioria das línguas: uma sequência de caracteres Unicode fechados em citações duplas, `"`.
Dentro de uma corda, o `\` de caracteres de corte traseiro pode ser usado para escapar a um personagem de citação dupla, e para inserir uma nova linha como `\n`, um retorno de carruagem como `\r`, e um separador como `\t`.
Por exemplo:

```qsharp
"\"Hello world!\", she said.\n"
```

A sintaxe Q# para interpolações de C# cordas é um subconjunto da sintaxe 7.0; Q# não suporta cordas interpoladas verbatim (multi-linhas).
Veja [*as Cordas Interpolated*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) para a C# sintaxe.

Expressões dentro de uma corda interpolada seguem C# Q# sintaxe, não sintaxe.
Qualquer expressão Q# válida pode aparecer numa corda interpolada.

## <a name="qubit-expressions"></a>Expressões Qubit

As únicas expressões `Qubit` são símbolos que estão ligados a `Qubit` valores ou elementos matrizes de `Qubit` matrizes.
Não há `Qubit` literal.

## <a name="pauli-expressions"></a>Expressões Pauli

Os quatro valores `Pauli`, `PauliI`, `PauliX`, `PauliY`e `PauliZ`, são todos expressões válidas `Pauli`.

Para além disso, as únicas expressões `Pauli` são símbolos que estão ligados a valores `Pauli` ou elementos matrizes de matrizes `Pauli`.

## <a name="result-expressions"></a>Expressões de Resultados

Os dois valores `Result`, `One` e `Zero`, são expressões válidas `Result`.

Para além disso, as únicas expressões `Result` são símbolos que estão ligados a valores `Result` ou elementos matrizes de matrizes `Result`.
Note-se, em particular, que `One` não é o mesmo que o `1`inteiro , e não existe uma conversão direta entre eles.
O mesmo se aplica aos `Zero` e `0`.

## <a name="range-expressions"></a>Expressões de alcance

Tendo em conta quaisquer três expressões `Int` `start`, `step`e `stop`, `start .. step .. stop` é uma expressão de alcance cujo primeiro elemento é `start`, o segundo elemento é `start+step`, o terceiro elemento é `start+step+step`, etc., até que `stop` seja passado.
Uma gama pode estar vazia se, por exemplo, `step` for positivo e `stop < start`.
O último elemento da gama será `stop` se a diferença entre `start` e `stop` for um múltiplo integral de `step`; ou seja, a gama é inclusiva em ambas as extremidades.

Tendo em conta duas expressões `Int` `start` e `stop`, `start .. stop` é uma expressão de alcance igual a `start .. 1 .. stop`.
Note que o `step` implícito é +1 mesmo que `stop` seja inferior a `start`; em tal caso, o alcance está vazio.

Algumas gamas de exemplo são:

- `1..3` é o intervalo 1, 2, 3.
- `2..2..5` é o intervalo 2, 4.
- `2..2..6` é o intervalo 2, 4, 6.
- `6..-2..2` é o intervalo 6, 4, 2.
- `2..1` é o alcance vazio.
- `2..6..7` é o intervalo 2.
- `2..2..1` é o alcance vazio.
- `1..-1..2` é o alcance vazio.

## <a name="callable-expressions"></a>Expressões Insensíveis

Um literal calivel é o nome de uma operação ou função definida no âmbito da compilação.
Por exemplo, `X` é uma operação literal que se refere à biblioteca padrão `X` operação, e `Message` é uma função literal que se refere à biblioteca padrão `Message` função.

Se uma operação suporta o functor `Adjoint`, então `Adjoint op` é uma expressão de operação.
Da mesma forma, se a operação suporta o functor `Controlled`, então `Controlled op` é uma expressão de operação.
Os tipos destas expressões são especificados em [Functors](xref:microsoft.quantum.language.type-model#functors).

Os functores (`Adjoint` e `Controlled`) ligam-se mais de perto do que todos os outros operadores, com exceção do `!` do operador desembrulhar e indexação de matriz com `[]`.
Assim, todos os seguintes são legais, assumindo que as operações apoiam os functors utilizados:

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

Um literal calivel pode ser usado como um valor, por exemplo, atribuir a uma variável ou passar para outra chamada.
Neste caso, se o callable tiver parâmetros de tipo, devem ser fornecidos como parte do valor calivel.
Um valor callable não pode ter nenhum tipo de parâmetros não especificados.

Por exemplo, se `Fun` for uma função com assinatura `'T1->Unit`:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expressões de invocação callable

Dada uma expressão (operação ou função) insensível e uma expressão de tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada através da adesão da expressão de tuple à expressão calúgica.
O tipo de expressão de invocação é o tipo de saída da assinatura do callable.

Por exemplo, se `Op` for uma operação com `((Int, Qubit) => Double)`de assinatura, `Op(3, qubit1)` é uma expressão de tipo `Double`.
Da mesma forma, se `Sin` é uma função com `(Double -> Double)`de assinatura, `Sin(0.1)` é uma expressão de tipo `Double`.
Finalmente, se `Builder` é uma função com assinatura `(Int -> (Int -> Int))`, então `Builder(3)` é uma função de Into to Int.

Invocar o resultado de uma expressão de valor calivel requer um par extra de parênteses em torno da expressão caluniável.
Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:

```qsharp
(Builder(3))(2)
```

Ao invocar uma chamada de tipo parametrizada, os parâmetros do tipo real podem ser especificados dentro dos suportes angulares `<` e `>` após a expressão caltável.
Isto é geralmente desnecessário, uma vez que o compilador Q# inferirá os tipos reais.
É necessário para aplicação parcial (ver abaixo) se um argumento de tipo parametrizado não for deixado não especificado.
Também é por vezes útil quando se passam operações com diferentes suportes de functor para um callable.

Por exemplo, se `Func` tiver `('T1, 'T2, 'T1) -> 'T2`de assinatura , `Op1` e `Op2` têm `(Qubit[] => Unit is Adj)`de assinatura , e `Op3` tem `(Qubit[] => Unit)`de assinatura , para invocar `Func` com `Op1` como primeiro argumento, `Op2` como o segundo, e `Op3` como o terceiro:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A especificação do tipo é necessária porque `Op3` e `Op1` têm tipos diferentes, por isso o compilador tratará isto como ambíguo sem a especificação.

### <a name="partial-application"></a>Aplicação parcial

Dada uma expressão calépável, um novo callable pode ser criado fornecendo um subconjunto dos argumentos ao callable.
Isto _chama-se aplicação parcial._

Em Q#, um callable parcialmente aplicado é expresso escrevendo uma expressão de invocação normal, mas usando um sublinhado, `_`, para os argumentos não especificados.
O chamador resultante tem o mesmo tipo de resultado que a base callable, e as mesmas especializações para operações.
O tipo de entrada da aplicação parcial é simplesmente o tipo original com os argumentos especificados removidos.

Se uma variável mutável for aprovada como um argumento especificado ao criar uma aplicação parcial, o valor atual da variável é usado.
A alteração do valor da variável posteriormente não terá impacto na aplicação parcial.

Por exemplo, se `Op` tiver tipo `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:

- `Op(5,(_,_))` tem `(((Qubit,Qubit), Double) => Unit is Adj)`tipo, assim como `Op(5,_)`.
- `Op(_,(_,1.0))` tem `((Int, (Qubit,Qubit)) => Unit is Adj)`tipo.
- `Op(_,((q1,q2),_))` tem `((Int,Double) => Unit is Adj)`tipo.
   Note que aplicamos equivalência de tuple singleton aqui.

Se o callable parcialmente aplicado tiver parâmetros de tipo que não podem ser inferidos pelo compilador, devem ser fornecidos no local de invocação.
A aplicação parcial não pode ter parâmetros de tipo não especificados.

Por exemplo, se `Op` tiver tipo `(('T1, Qubit, 'T1) => Unit : Adjoint)`:

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>Recursão

Q# os callables são permitidos ser direta ou indiretamente recursivos.
Ou seja, uma operação ou função pode chamar-se a si mesma, ou pode chamar outra chamada que, direta ou indiretamente, chama a operação de chamada.

No entanto, existem dois comentários importantes sobre a recura:

- A utilização da recursição nas operações é suscetível de interferir com determinadas otimizações.
  Isto pode ter um impacto substancial no tempo de execução do algoritmo.
- Ao executar um dispositivo quântico real, o espaço da pilha pode ser limitado, e assim a recursão profunda pode levar a um erro de tempo de execução.
  Em particular, o compilador Q# e o tempo de execução não identificam e otimizam a recursão da cauda.

## <a name="tuple-expressions"></a>Expressões tuple

Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas em `(` e `)`.
Por exemplo, `(1, One)` é uma expressão `(Int, Result)`.

Além dos literais, as únicas expressões de tuple são símbolos que estão ligados a valores de tuple, elementos marray de matrizes de tuple, e invocações calíveis que devolvem tuples.

## <a name="user-defined-type-expressions"></a>Expressões de tipo definidas pelo utilizador

Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.
Por exemplo, se `IntPair` é um tipo definido pelo utilizador com base em `(Int, Int)`, então `IntPair(2,3)` seria um literal válido desse tipo.

Para além dos literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos manuais de matrizes desse tipo, e invocações calíveis que devolvem esse tipo.

## <a name="unwrap-expressions"></a>Desembrulhar Expressões

Em Q#, o operador de desembrulhar é um ponto de exclamação `!`.
Por exemplo, se `IntPair` é um tipo definido pelo utilizador com `(Int, Int)`de tipo subjacente, e `s` era uma variável com valor `IntPair(2,3)`, então `s!` seria `(2,3)`.

Para tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador. O operador de desembrulhar pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s`.
Assim, se `WrappedPair` é um tipo definido pelo utilizador com `IntPair`de tipo subjacente, e `t` é uma variável com valor `WrappedPair(IntPair(1,2))`, então `t!!` seria `(1,2)`.

O operador `!` tem uma precedência maior do que todos os outros operadores que não `[]` para indexação e corte de matriz.
`!` e `[]` ligar posicionalmente; ou seja, `a[i]![3]` deve ser lido como `((a[i])!)[3]`: tome o `i`'th elemento de `a`, desembrulhe-o, e, em seguida, obtenha o 3º elemento do valor desembrulhado (que deve ser uma matriz).

A precedência do operador `!` tem um impacto que pode não ser óbvio.
Se uma função ou operação devolver um valor que depois seja desembrulhado, a função ou chamada de operação deve ser encerrada em parênteses de modo a que o argumento se ligue à chamada e não ao desembrulhar.
Por exemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expressões de matriz

Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas em `[` e `]`.
Todos os elementos devem ser compatíveis com o mesmo tipo.

Se o tipo de elemento comum for um tipo de funcionamento ou de função, todos os elementos devem ter os mesmos tipos de entrada e saída.
O tipo de elemento da matriz irá suportar todos os functors que sejam suportados por todos os elementos.
Por exemplo, se `Op1`, `Op2`e `Op3` todos forem `Qubit[] => Unit`, mas `Op1` apoia `Adjoint`, `Op2` apoia `Controlled`, e `Op3` apoia ambos:

- `[Op1, Op2]` é uma série de operações `(Qubit[] => Unit)`.
- `[Op1, Op3]` é uma série de operações `(Qubit[] => Unit is Adj)`.
- `[Op2, Op3]` é uma série de operações `(Qubit[] => Unit is Ctl)`.

Não são permitidos os literais vazios, `[]`, não são permitidos.
Em vez disso, a utilização de `new ★[0]`, onde `★` é um espaço reservado para um tipo adequado, permite criar a matriz de comprimento zero desejada.

Tendo em conta duas matrizes do mesmo tipo, o operador de `+` binário pode ser usado para formar uma nova matriz que é a concatenação das duas matrizes.
Por exemplo, `[1,2,3] + [4,5,6]` é `[1,2,3,4,5,6]`.

### <a name="array-creation"></a>Criação de Matriz

Dado um tipo e uma expressão `Int`, o operador `new` pode ser utilizado para alocar um novo conjunto do tamanho dado.
Por exemplo, `new Int[i+1]` atribuiria um novo conjunto de `Int` com elementos `i+1`.

Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.
Na maioria dos casos, esta é uma variação de zero.

Para qubits e callables, que são referências a entidades, não existe um valor razoável por defeito.
Assim, para estes tipos, a predefinição é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.
Isto é semelhante a uma referência C# nula em línguas como ou Java.
As matrizes que contenham qubits ou callables devem ser corretamente inicializadas com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança. As rotinas de inicialização adequadas podem ser encontradas em <xref:microsoft.quantum.arrays>.

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
 `Range` | O alcance vazio, `1..1..0`
 `Callable` | _inválido callable_
 `Array['T]` | `'T[0]`

Os tipos tuple são inicializados elemento a elemento.


### <a name="jagged-arrays"></a>Matrizes Irregulares

Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes. Os elementos de uma matriz irregular podem ser de diferentes tamanhos. O exemplo que se segue mostra como declarar e inicializar uma matriz irregular representando uma tabela de multiplicação.

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


### <a name="array-slices"></a>Fatias de matriz

Dada a expressão da matriz e uma expressão `Range`, pode formar-se uma nova expressão utilizando o operador de `[` e `]` fatiade matriz.
A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range`, na ordem definida pelo `Range`.
Por exemplo, se `a` está ligada a uma série de `Double`s, então `a[3..-1..0]` é uma expressão `Double[]` que contém os primeiros quatro elementos de `a` mas na ordem inversa, como aparecem em `a`.

Se o `Range` estiver vazio, então a fatia de matriz resultante será de zero comprimento.

Se a expressão da matriz não for um identificador simples, deve ser fechada a parênteses para cortar.
Por exemplo, se `a` e `b` forem ambos conjuntos de `Int`s, uma fatia da concatenação seria expressa como:

```qsharp
(a+b)[1..2..7]
```

Todas as matrizes em Q# são baseadas em zero.
Ou seja, o primeiro elemento de uma matriz `a` é sempre `a[0]`.

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

## <a name="array-element-expressions"></a>Expressões do elemento matriz

Dada a expressão da matriz e uma expressão `Int`, pode ser formada uma nova expressão utilizando o operador de elementos de `[` e `]` matriz.
A nova expressão será do mesmo tipo que o tipo de elemento da matriz.
Por exemplo, se `a` está ligada a uma série de `Double`s, então `a[4]` é uma expressão `Double`.

Se a expressão da matriz não for um identificador simples, deve ser fechada a sua parênteses para selecionar um elemento.
Por exemplo, se `a` e `b` forem ambos conjuntos de `Int`s, um elemento da constcatenação seria expresso como:

```qsharp
(a+b)[13]
```

Todas as matrizes em Q# são baseadas em zero.
Ou seja, o primeiro elemento de uma matriz `a` é sempre `a[0]`.


## <a name="copy-and-update-expressions"></a>Expressões de cópia e atualização

Novas matrizes podem ser criadas a partir das existentes através de expressões de cópia e atualização.
Uma expressão de cópia e atualização é uma expressão do formulário `expression1 w/ expression2 <- expression3`, onde `expression1` tem de ser de tipo `T[]` para algum tipo `T`. A segunda `expression2` define os índices dos elementos a modificar em comparação com a matriz em `expression1` e tem de ser de tipo `Int` ou de `Range`tipo . Se `expression2` for de tipo `Int`, `expression3` tem de ser do tipo `T`. Se `expression2` for de tipo `Range`, `expression3` tem de ser do tipo `T[]`.

Uma expressão de cópia e atualização `arr w/ idx <- value` constrói um novo conjunto com todos os elementos definidos para o elemento correspondente em `arr`, com exceção dos elementos `idx`, que estão definidos para os ou os `value`. Por exemplo, se `arr` contém uma matriz `[0,1,2,3]`, então 
- `arr w/ 0 <- 10` é a matriz `[10,1,2,3]`.
- `arr w/ 2 <- 10` é a matriz `[0,1,10,3]`.
- `arr w/ 0..2..3 <- [10,12]` é a matriz `[10,1,12,3]`.

Existem expressões semelhantes para itens nomeados em tipos definidos pelo utilizador. Considere, por exemplo, o tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Se `c` contém o valor do tipo `Complex(1.,-1.)`, então `c w/ Re <- 0.` é uma expressão de tipo `Complex` que avalia para `Complex(0.,-1.)`.

## <a name="conditional-expressions"></a>Expressões Condicionais

Tendo em conta duas outras expressões do mesmo tipo e uma expressão booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação `?` e a barra vertical `|`.
Por exemplo, `a==b ? c | d`.
Neste exemplo, o valor da expressão condicional será `c` se `a==b` for verdade e `d` se for falsa.

As duas expressões podem avaliar para operações que tenham as mesmas inputs e saídas, mas suportam diferentes functores.
Neste caso, o tipo de expressão condicional é uma operação com as inputs e saídas que suporta todos os functors suportados por ambas as expressões.
Por exemplo, se `Op1`, `Op2`e `Op3` todos forem `Qubit[]=>Unit`, mas `Op1` apoia `Adjoint`, `Op2` apoia `Controlled`, e `Op3` apoia ambos:

- `flag ? Op1 | Op2` é uma operação `(Qubit[] => Unit)`.
- `flag ? Op1 | Op3` é uma operação `(Qubit[] => Unit is Adj)`.
- `flag ? Op2 | Op3` é uma operação `(Qubit[] => Unit is Ctl)`.

Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de operação, essa chamada só ocorrerá se esse resultado for o valor da chamada.
Por exemplo, no caso `a==b ? C(qs) | D(qs)`, se `a==b` for verdade, então a operação `C` será invocada, e se for falsa, então apenas `D` serão invocadas.
Isto é semelhante ao curto-circuito noutras línguas.


## <a name="operator-precedence"></a>Precedência do operador

Todos os operadores binários são associativos de direito, com exceção `^`.

Os suportes, `[` e `]`, para corte e indexação de matrizes, ligam-se perante qualquer operador.

Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.

Os parênteses para a exploração e a invocação de funções também se ligam perante qualquer operador, mas após a indexação da matriz e functores.

Operadores por ordem de precedência, dos mais elevados aos mais baixos:

Operador | Rio Arity | Descrição | Tipos de operand
---------|----------|---------|---------------
 `!` de rasto | Unary | Desembrulhar | Qualquer tipo definido pelo utilizador
 `-`, `~~~`, `not` | Unary | Negativa numérica, um complemento bitwise, negação lógica | `Int`, `BigInt` ou `Double` para `-`, `Int` ou `BigInt` para `~~~`, `Bool` para `not`
 `^` | Binário | Poder inteiro | `Int` ou `BigInt` para a base, `Int` para o expoente
 `/`, `*`, `%` | Binário | Divisão, multiplicação, modulo inteiro | `Int`, `BigInt` ou `Double` para `/` e `*`, `Int` ou `BigInt` para `%`
 `+`, `-` | Binário | Adição ou cadeia e concatenação de cordas, subtração | `Int`, `BigInt` ou `Double`, adicionalmente `String` ou qualquer tipo de matriz para `+`
 `<<<`, `>>>` | Binário | Turno da esquerda, turno da direita | `Int` ou `BigInt`
 `<`, `<=`, `>`, `>=` | Binário | Comparações menos ou iguais, mais do que iguais, maiores do que iguais ou iguais | `Int`, `BigInt` ou `Double`
 `==`, `!=` | Binário | comparações iguais e não iguais | qualquer tipo primitivo
 `&&&` | Binário | Bitwise E | `Int` ou `BigInt`
 `^^^` | Binário | Bitwise XOR | `Int` ou `BigInt`
 <code>\|\|\|</code> | Binário | Bitwise OU | `Int` ou `BigInt`
 `and` | Binário | Lógico E | `Bool`
 `or` | Binário | Lógica OU | `Bool`
 `..` | Binário/Ternary | Operador de gama | `Int`
 `?` `|` | Ternário | Condicional | `Bool` para o lado esquerdo
`w/` `<-` | Ternário | Cópia e atualização | ver [expressões de cópia e atualização](#copy-and-update-expressions)
