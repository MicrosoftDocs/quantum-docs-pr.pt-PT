---
title: Q# Expressões
description: Compreenda como especificar, referenciar e combinar constantes, variáveis, operadores, operações e funções como expressões em Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683932"
---
# <a name="expressions"></a>Expressões

## <a name="grouping"></a>Agrupamento

Dada qualquer expressão, essa mesma expressão em parênteses é uma expressão do mesmo tipo.
Por exemplo, `(7)` `Int` é `([1,2,3])` uma expressão, é `Int`uma expressão `((1,2))` de tipo `(Int, Int)`de matriz de s, e é uma expressão com tipo .

A equivalência entre valores simples e tuples de um único `(6)` elemento descrito `(6)` no modelo do [tipo](xref:microsoft.quantum.language.type-model#tuple-types) remove a ambiguidade entre um grupo e como um túnica de um único elemento.

## <a name="symbols"></a>Símbolos

O nome de um símbolo ligado ou `'T` atribuído a um `'T`valor de tipo é uma expressão de tipo .
Por exemplo, se `count` o símbolo está ligado `5`ao `count` valor inteiro, então é uma expressão inteiro.

## <a name="numeric-expressions"></a>Expressões numéricas

Expressões numéricas são `Int`expressões de tipo, `BigInt`ou `Double`.
Ou são números inteiros ou flutuantes.

`Int`os literais em Q# são idênticos aos literais inteiros em C#, exceto que não é necessário seguir "l" ou "L" (ou permitido).
Os inteiros hexadecimais e binários são suportados com um prefixo "0x" e "0b", respectivamente.

`BigInt`os literais em Q# são idênticos a grandes cordas inteiros em .NET, com um "l" ou "L".
Os grandes inteiros hexadecimais são suportados com um prefixo "0x".
Assim, todos os seguintes `BigInt` são usos válidos de literais:

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`os literais em Q# são idênticos aos duplos literais em C#, exceto que não é necessário seguir "d" ou "D" (ou permitido).

Dada a expressão da matriz de qualquer tipo de elemento, pode ser formada `Int` uma expressão utilizando a `Length` função incorporada, com a expressão da matriz fechada em parênteses, `(` e `)`.
Por exemplo, `a` se está ligado `Length(a)` a uma matriz, então é uma expressão inteiro.
Se `b` for um conjunto de conjuntos `Int[][]`de `Length(b)` inteiros, então é `b`o `Length(b[1])` número de sub-arrays em , e `b`é o número de inteiros na segunda sub-matriz em .

Tendo em conta duas expressões numéricas `+`do `-` `*`mesmo `/` tipo, os operadores binários, e podem ser usados para formar uma nova expressão numérica.
O tipo da nova expressão será o mesmo que os tipos das expressões constituintes.

Tendo em conta duas expressões inteiros, o operador `^` binário (potência) pode ser utilizado para formar uma nova expressão inteiro.
Da mesma `^` forma, pode ser usado com duas expressões duplas para formar uma nova expressão dupla.
Finalmente, `^` pode ser usado com uma grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão inteiro.
Neste caso, o segundo parâmetro deve caber em 32 bits; se não, um erro de tempo de execução será levantado.

Tendo em conta duas expressões inteiros ou grandes inteiros, uma nova expressão inteiro `%` ou grande `&&&` inteiro pode ser `|||` formada usando `^^^` os operadores (modulo), (bitwise And), (bitwise OR), ou (bitwise XOR).

Dado um inteiro ou uma expressão inteiro à esquerda, e uma expressão inteiro `<<<` à direita, os operadores (mudança de esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão esquerda.

O segundo parâmetro (o valor de deslocação) para uma das operações por turnos deve ser maior ou igual a zero; o comportamento para quantidades de mudança negativa é indefinido.
O montante de deslocação para qualquer uma das operações por turnos também deve caber em 32 bits; se não, um erro de tempo de execução será levantado.
Se o número a deslocar for um inteiro, então `mod 64`o valor do turno é interpretado; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.

Tanto para valores inteiros como para grandes valores inteiros, as mudanças são aritméticas.
Mudar um valor negativo, quer à esquerda quer à direita, resultará num número negativo.
Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.

Divisão integer e modulo inteiro seguem o mesmo comportamento para números negativos que C#.
Ou `a % b` seja, terá sempre o `a`mesmo `b * (a / b) + a % b` sinal `a`que , e sempre será igual .
Por exemplo:

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

A grande divisão de inteiros e o modulo funcionam da mesma forma.

Dada qualquer expressão numérica, pode `-` ser formada uma nova expressão utilizando o operador não-eléctrico.
A nova expressão será do mesmo tipo que a expressão constituinte.

Dada a expressão inteiro ou grande inteiro, pode formar-se uma `~~~` nova expressão do mesmo tipo utilizando o (complemento bitwise) do operador não-secundário.

## <a name="boolean-expressions"></a>Expressões booleanas

Os `Bool` dois valores literais são `true` e. `false`

Dadas duas expressões do mesmo `==` tipo `!=` primitivo, os operadores `Bool` binários e binários podem ser utilizados para construir uma expressão.
A expressão será verdadeira se as duas expressões forem iguais, e falsas se não forem.

Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores não embrulhados podem ser comparados. Por exemplo, utilizando o operador `!` "desembrulhar" (explicado na página do [modelo do tipo Q#](xref:microsoft.quantum.language.type-model#user-defined-types)),

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

A comparação da igualdade de `Qubit` valores é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.
O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.

A comparação da igualdade de `Double` valores pode ser enganosa devido aos efeitos arredondamentos.
Por exemplo, `49.0 * (1.0/49.0) != 1.0`.

Tendo em conta duas expressões numéricas, `>`os operadores `<`binários, `>=`e `<=` podem ser utilizados para construir uma nova expressão booleana que seja verdadeira se a primeira expressão for respectivamente maior do que, inferior ou igual, ou inferior ou igual ou igual à segunda expressão.

Dadas duas expressões booleanas, os `and` operadores e `or` binários podem ser usados para construir uma nova expressão booleana que é verdade se ambos (resp. ou ambos) as duas expressões forem verdadeiras.

Dada qualquer expressão `not` booleana, o operador não-secundário pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.

## <a name="string-expressions"></a>Expressões de cordas

Q# permite que as cordas `fail` sejam `Log` usadas na declaração e na função padrão.

As cordas em Q# são literais ou cordas interpoladas.
Os literais de cordas são semelhantes aos simples literais de cordas na `"`maioria das línguas: uma sequência de caracteres Unicode fechados em citações duplas, .
Dentro de uma corda, o `\` personagem de corte traseiro pode ser usado para `\n`escapar a um `\r`personagem de `\t`citação dupla, e para inserir uma nova linha como , um retorno de carruagem como , e um separador como .
Por exemplo:

```qsharp
"\"Hello world!\", she said.\n"
```

A sintaxe Q# para interpolações de cordas é um subconjunto da sintaxe C# 7.0; Q# não suporta cordas interpoladas verbatim (multi-linhas).
Ver [*Cordas Interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) para a sintaxe C#

Expressões dentro de uma corda interpolada seguem Q# sintaxe, não C# sintaxe.
Qualquer expressão Q# válida pode aparecer numa corda interpolada.

## <a name="qubit-expressions"></a>Expressões Qubit

As `Qubit` únicas expressões são símbolos que estão ligados a `Qubit` valores ou elementos matrizes de `Qubit` matrizes.
Não há `Qubit` literal.

## <a name="pauli-expressions"></a>Expressões Pauli

Os `Pauli` quatro `PauliI` `PauliX`valores, `PauliY` `PauliZ`e, são `Pauli` todas expressões válidas.

Além disso, `Pauli` as únicas expressões são `Pauli` símbolos que `Pauli` estão ligados a valores ou elementos matrizes de matrizes.

## <a name="result-expressions"></a>Expressões de Resultados

Os `Result` dois `One` valores, `Zero` `Result` e, são expressões válidas.

Além disso, `Result` as únicas expressões são `Result` símbolos que `Result` estão ligados a valores ou elementos matrizes de matrizes.
Em particular, note que não é o mesmo que `One` o inteiro `1`, e não há conversão direta entre eles.
O mesmo se `Zero` `0`aplica a e.

## <a name="range-expressions"></a>Expressões de alcance

Dadas `Int` as `start`três `step`expressões, `stop`e é `start .. step .. stop` uma `start`expressão de `start+step`alcance cujo `start+step+step`primeiro elemento é `stop` , o segundo elemento é , o terceiro elemento é , etc., até que seja passado.
Uma gama pode estar vazia `step` se, `stop < start`por exemplo, for positiva e .
O último elemento da `stop` gama será `start` se `stop` a diferença `step`entre e for um múltiplo integral de; ou seja, a gama é inclusiva em ambas as extremidades.

Dadas `Int` duas `start` expressões e, `stop` `start .. stop` é uma `start .. 1 .. stop`expressão de alcance que é igual a .
Note que `step` o implícito é `stop` +1 `start`mesmo que seja inferior a; em tal caso, o alcance está vazio.

Algumas gamas de exemplo são:

- `1..3`é o intervalo 1, 2, 3.
- `2..2..5`é o intervalo 2, 4.
- `2..2..6`é o intervalo 2, 4, 6.
- `6..-2..2`é o alcance 6, 4, 2.
- `2..1`é o alcance vazio.
- `2..6..7`é o intervalo 2.
- `2..2..1`é o alcance vazio.
- `1..-1..2`é o alcance vazio.

## <a name="callable-expressions"></a>Expressões Insensíveis

Um literal calivel é o nome de uma operação ou função definida no âmbito da compilação.
Por `X` exemplo, é uma operação literal que `X` se `Message` refere à operação padrão da biblioteca, e é uma função literal que se refere à função padrão da biblioteca. `Message`

Se uma operação `Adjoint` suporta o functor, então `Adjoint op` é uma expressão de operação.
Da mesma forma, se `Controlled` a operação suporta `Controlled op` o functor, então é uma expressão de operação.
Os tipos destas expressões são especificados em [Functors](xref:microsoft.quantum.language.type-model#functors).

Os functores (e)`Adjoint` ligam-se `Controlled`mais estreitamente do `!` que todos os `[]`outros operadores, com exceção do operador de desembrulhar e da indexação da matriz com .
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

Por exemplo, `Fun` se for `'T1->Unit`uma função com assinatura:

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>Expressões de invocação callable

Dada uma expressão (operação ou função) insensível e uma expressão de tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada através da adesão da expressão de tuple à expressão calúgica.
O tipo de expressão de invocação é o tipo de saída da assinatura do callable.

Por exemplo, `Op` se for `((Int, Qubit) => Double)`uma `Op(3, qubit1)` operação com `Double`assinatura, é uma expressão de tipo .
Da mesma `Sin` forma, se `(Double -> Double)`for `Sin(0.1)` uma função `Double`com assinatura, é uma expressão de tipo .
Finalmente, `Builder` se é uma `(Int -> (Int -> Int))`função com assinatura, então `Builder(3)` é uma função de Into to Int.

Invocar o resultado de uma expressão de valor calivel requer um par extra de parênteses em torno da expressão caluniável.
Assim, para invocar o `Builder` resultado da chamada do parágrafo anterior, a sintaxe correta é:

```qsharp
(Builder(3))(2)
```

Ao invocar uma chamada de tipo parametrizada, os parâmetros do `<` tipo `>` real podem ser especificados dentro dos suportes angulares e após a expressão caltável.
Isto é geralmente desnecessário, uma vez que o compilador Q# inferirá os tipos reais.
É necessário para aplicação parcial (ver abaixo) se um argumento de tipo parametrizado não for deixado não especificado.
Também é por vezes útil quando se passam operações com diferentes suportes de functor para um callable.

Por exemplo, `Func` se `('T1, 'T2, 'T1) -> 'T2` `Op1` tiver `Op2` assinatura `(Qubit[] => Unit is Adj)`, `Op3` e `(Qubit[] => Unit)`tiver `Func` assinatura `Op1` , e `Op2` tiver assinatura , `Op3` para invocar como primeiro argumento, como o segundo, e como o terceiro:

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

A especificação do `Op3` tipo `Op1` é necessária porque e tem tipos diferentes, por isso o compilador tratará isto como ambíguo sem a especificação.

### <a name="partial-application"></a>Aplicação parcial

Dada uma expressão calépável, um novo callable pode ser criado fornecendo um subconjunto dos argumentos ao callable.
Isto _chama-se aplicação parcial._

Em Q#, um callable parcialmente aplicado é expresso escrevendo uma expressão `_`de invocação normal, mas usando um sublinhado, para os argumentos não especificados.
O chamador resultante tem o mesmo tipo de resultado que a base callable, e as mesmas especializações para operações.
O tipo de entrada da aplicação parcial é simplesmente o tipo original com os argumentos especificados removidos.

Se uma variável mutável for aprovada como um argumento especificado ao criar uma aplicação parcial, o valor atual da variável é usado.
A alteração do valor da variável posteriormente não terá impacto na aplicação parcial.

Por exemplo, `Op` se `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`tiver tipo:

- `Op(5,(_,_))`tem `(((Qubit,Qubit), Double) => Unit is Adj)`tipo, assim `Op(5,_)`como.
- `Op(_,(_,1.0))`tem `((Int, (Qubit,Qubit)) => Unit is Adj)`tipo .
- `Op(_,((q1,q2),_))`tem `((Int,Double) => Unit is Adj)`tipo .
   Note que aplicamos equivalência de tuple singleton aqui.

Se o callable parcialmente aplicado tiver parâmetros de tipo que não podem ser inferidos pelo compilador, devem ser fornecidos no local de invocação.
A aplicação parcial não pode ter parâmetros de tipo não especificados.

Por exemplo, `Op` se `(('T1, Qubit, 'T1) => Unit : Adjoint)`tiver tipo:

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

Um tuple literal é uma sequência de expressões de elementos do `(` tipo `)`apropriado, separadas por vírgulas, fechadas e .
Por exemplo, `(1, One)` `(Int, Result)` é uma expressão.

Além dos literais, as únicas expressões de tuple são símbolos que estão ligados a valores de tuple, elementos marray de matrizes de tuple, e invocações calíveis que devolvem tuples.

## <a name="user-defined-type-expressions"></a>Expressões de tipo definidas pelo utilizador

Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.
Por exemplo, `IntPair` se for um tipo `(Int, Int)`definido `IntPair(2,3)` pelo utilizador com base, então seria um literal válido desse tipo.

Para além dos literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos manuais de matrizes desse tipo, e invocações calíveis que devolvem esse tipo.

## <a name="unwrap-expressions"></a>Desembrulhar Expressões

Em Q#, o operador de desembrulhar `!`é um ponto de exclamação de trailing .
Por exemplo, `IntPair` se for um tipo `(Int, Int)`definido `s` pelo utilizador com `IntPair(2,3)`tipo `s!` subjacente, e fosse uma variável com valor, então seria `(2,3)`.

Para tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador. O operador de desembrulhar pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s`.
Assim, `WrappedPair` se for um tipo definido `IntPair`pelo `t` utilizador com `WrappedPair(IntPair(1,2))`tipo `t!!` subjacente, `(1,2)`e for uma variável com valor, então seria .

O `!` operador tem uma precedência maior `[]` do que todos os outros operadores que não o índice de matriz e o corte.
`!`e `[]` ligar posicionalmente; isto `a[i]![3]` é, deve `((a[i])!)[3]`ser lido `i`como : `a`pegue o 'elemento de, desembrulhe-o, e, em seguida, obtenha o 3º elemento do valor desembrulhado (que deve ser uma matriz).

A precedência `!` do operador tem um impacto que pode não ser óbvio.
Se uma função ou operação devolver um valor que depois seja desembrulhado, a função ou chamada de operação deve ser encerrada em parênteses de modo a que o argumento se ligue à chamada e não ao desembrulhar.
Por exemplo:

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>Expressões de matriz

Uma matriz literal é uma sequência de uma ou mais expressões `[` `]`de elementos, separadas por vírgulas, fechadas e .
Todos os elementos devem ser compatíveis com o mesmo tipo.

Se o tipo de elemento comum for um tipo de funcionamento ou de função, todos os elementos devem ter os mesmos tipos de entrada e saída.
O tipo de elemento da matriz irá suportar todos os functors que sejam suportados por todos os elementos.
Por exemplo, `Op1` `Op2`se `Op3` , `Qubit[] => Unit`e `Op1` todos `Adjoint`são `Op2` , `Controlled`mas `Op3` apoia , apoia , e apoia ambos:

- `[Op1, Op2]`é uma `(Qubit[] => Unit)` série de operações.
- `[Op1, Op3]`é uma `(Qubit[] => Unit is Adj)` série de operações.
- `[Op2, Op3]`é uma `(Qubit[] => Unit is Ctl)` série de operações.

Não são permitidos os literais vazios. `[]`
Em `new ★[0]`vez `★` disso, a utilização, onde é o espaço reservado para um tipo adequado, permite criar a matriz de comprimento zero desejada.

Tendo em conta duas matrizes `+` do mesmo tipo, o operador binário pode ser usado para formar uma nova matriz que é a concatenação das duas matrizes.
Por `[1,2,3] + [4,5,6]` exemplo, `[1,2,3,4,5,6]`é.

### <a name="array-creation"></a>Criação de Matriz

Dado um `Int` tipo e `new` uma expressão, o operador pode ser utilizado para alocar um novo conjunto do tamanho dado.
Por exemplo, `new Int[i+1]` atribuiria uma nova `Int` matriz com `i+1` elementos.

Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.
Na maioria dos casos, esta é uma variação de zero.

Para qubits e callables, que são referências a entidades, não existe um valor razoável por defeito.
Assim, para estes tipos, a predefinição é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.
Isto é semelhante a uma referência nula em línguas como C# ou Java.
As matrizes que contenham qubits ou callables devem ser corretamente inicializadas com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança. Podem ser encontradas rotinas <xref:microsoft.quantum.arrays>de inicialização adequadas em .

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

Dada a expressão `Range` da matriz e uma `[` expressão, pode formar-se uma nova expressão utilizando o operador de fatias de matriz e matriz. `]`
A nova expressão será do mesmo tipo que a matriz e conterá os `Range`itens de matriz `Range`indexados pelos elementos do , na ordem definida pela .
Por exemplo, `a` se está ligado `Double`a `a[3..-1..0]` uma `Double[]` série de s, então `a` é uma expressão que `a`contém os primeiros quatro elementos de mas na ordem inversa como eles aparecem em .

Se `Range` a estiver vazia, então a fatia de matriz resultante será de zero comprimento.

Se a expressão da matriz não for um identificador simples, deve ser fechada a parênteses para cortar.
Por exemplo, `a` `b` se e ambos `Int`forem ambos os conjuntos de s, uma fatia da concatenação seria expressa como:

```qsharp
(a+b)[1..2..7]
```

Todas as matrizes em Q# são baseadas em zero.
Ou seja, o primeiro `a` elemento `a[0]`de uma matriz é sempre.

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

Dada a expressão `Int` da matriz e uma `[` expressão, pode formar-se uma nova expressão utilizando o operador de elementos de matriz e matriz. `]`
A nova expressão será do mesmo tipo que o tipo de elemento da matriz.
Por exemplo, `a` se está ligado `Double`a `a[4]` uma `Double` série de s, então é uma expressão.

Se a expressão da matriz não for um identificador simples, deve ser fechada a sua parênteses para selecionar um elemento.
Por exemplo, `a` `b` se e ambos `Int`forem conjuntos de s, um elemento da concatenação seria expresso como:

```qsharp
(a+b)[13]
```

Todas as matrizes em Q# são baseadas em zero.
Ou seja, o primeiro `a` elemento `a[0]`de uma matriz é sempre.


## <a name="copy-and-update-expressions"></a>Expressões de cópia e atualização

Novas matrizes podem ser criadas a partir das existentes através de expressões de cópia e atualização.
Uma expressão de cópia e atualização `expression1 w/ expression2 <- expression3`é `expression1` uma expressão do `T[]` formulário, `T`onde tem de ser de tipo para algum tipo . O `expression2` segundo define os índices dos elementos a modificar em `expression1` comparação com `Int` a matriz e tem de ser de tipo ou de tipo `Range`. Se `expression2` for `Int`de `expression3` tipo, tem `T`de ser de tipo. Se `expression2` for `Range`de `expression3` tipo, tem `T[]`de ser de tipo.

Uma `arr w/ idx <- value` expressão de cópia e atualização constrói uma nova matriz `arr`com todos os elementos `idx`definidos para o elemento correspondente, `value`com exceção dos elementos em , que estão definidos para os ou os em . Por exemplo, `arr` se `[0,1,2,3]`contiver uma matriz, então 
- `arr w/ 0 <- 10`é a `[10,1,2,3]`matriz.
- `arr w/ 2 <- 10`é a `[0,1,10,3]`matriz.
- `arr w/ 0..2..3 <- [10,12]`é a `[10,1,12,3]`matriz.

Existem expressões semelhantes para itens nomeados em tipos definidos pelo utilizador. Considere, por exemplo, o tipo 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
Se `c` contiver o `Complex(1.,-1.)`valor `c w/ Re <- 0.` do tipo, `Complex` então `Complex(0.,-1.)`é uma expressão de tipo que avalia para .

## <a name="conditional-expressions"></a>Expressões Condicionais

Tendo em conta duas outras expressões do mesmo tipo e uma expressão `?` booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação e a barra `|`vertical .
Por exemplo, `a==b ? c | d`.
Neste exemplo, o valor da expressão `c` `a==b` condicional será `d` se for verdade e se for falso.

As duas expressões podem avaliar para operações que tenham as mesmas inputs e saídas, mas suportam diferentes functores.
Neste caso, o tipo de expressão condicional é uma operação com as inputs e saídas que suporta todos os functors suportados por ambas as expressões.
Por exemplo, `Op1` `Op2`se `Op3` , `Qubit[]=>Unit`e `Op1` todos `Adjoint`são `Op2` , `Controlled`mas `Op3` apoia , apoia , e apoia ambos:

- `flag ? Op1 | Op2`é `(Qubit[] => Unit)` uma operação.
- `flag ? Op1 | Op3`é `(Qubit[] => Unit is Adj)` uma operação.
- `flag ? Op2 | Op3`é `(Qubit[] => Unit is Ctl)` uma operação.

Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de operação, essa chamada só ocorrerá se esse resultado for o valor da chamada.
Por exemplo, no `a==b ? C(qs) | D(qs)`caso, se `a==b` `C` for verdade, a operação será invocada, e se for falsa, só `D` será invocada.
Isto é semelhante ao curto-circuito noutras línguas.


## <a name="operator-precedence"></a>Precedência do operador

Todos os operadores binários são `^`associativos de direito, exceto .

Os suportes `]`e, `[` para cortar matrize e indexação, ligam-se perante qualquer operador.

Os `Adjoint` functores `Controlled` e ligam-se após a indexação da matriz, mas antes de todos os outros operadores.

Os parênteses para a exploração e a invocação de funções também se ligam perante qualquer operador, mas após a indexação da matriz e functores.

Operadores por ordem de precedência, dos mais elevados aos mais baixos:

Operador | Rio Arity | Descrição | Tipos de operand
---------|----------|---------|---------------
 arrastando`!` | Unary | Desembrulhar | Qualquer tipo definido pelo utilizador
 `-`, `~~~`, `not` | Unary | Negativa numérica, um complemento bitwise, negação lógica | `Int`, `BigInt` `Double` ou `-` `Int` para, `~~~` `Bool` ou `BigInt` para, para`not`
 `^` | Binário | Poder inteiro | `Int`ou `BigInt` para a `Int` base, para o expoente
 `/`, `*`, `%` | Binário | Divisão, multiplicação, modulo inteiro | `Int`, `BigInt` `Double` ou `/` `*`para `Int` `BigInt` e, ou para`%`
 `+`, `-` | Binário | Adição ou cadeia e concatenação de cordas, subtração | `Int`, `BigInt` `Double`ou, `String` adicionalmente ou qualquer tipo de matriz para`+`
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
