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
# <a name="type-expressions-in-q"></a><span data-ttu-id="1db1f-103">Expressãos tipo em Q #</span><span class="sxs-lookup"><span data-stu-id="1db1f-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="1db1f-104">Expressões numéricas</span><span class="sxs-lookup"><span data-stu-id="1db1f-104">Numeric Expressions</span></span>

<span data-ttu-id="1db1f-105">Expressões numéricas são expressões do `Int` `BigInt` tipo, ou `Double` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="1db1f-106">Ou seja, ou são números inteiros ou de pontos flutuantes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="1db1f-107">`Int`literais em Q# são escritos simplesmente como uma sequência de dígitos.</span><span class="sxs-lookup"><span data-stu-id="1db1f-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="1db1f-108">Os inteiros hexadecimais e binários são suportados com um `0x` `0b` e prefixo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1db1f-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="1db1f-109">`BigInt`literais em Q# são escritos com um rasto `l` ou `L` sufixo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="1db1f-110">Os grandes inteiros hexadecimais são suportados com um prefixo "0x".</span><span class="sxs-lookup"><span data-stu-id="1db1f-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="1db1f-111">Assim, todas são utilizações válidas de `BigInt` literais:</span><span class="sxs-lookup"><span data-stu-id="1db1f-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="1db1f-112">`Double`literais em Q# são números de ponto flutuante escritos usando dígitos decimais.</span><span class="sxs-lookup"><span data-stu-id="1db1f-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="1db1f-113">Podem ser escritos com um ponto decimal, `.` e/ou uma parte exponencial indicada com 'e' ou 'E' (após o qual apenas são válidos um possível sinal negativo e dígitos decimais).</span><span class="sxs-lookup"><span data-stu-id="1db1f-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="1db1f-114">Seguem-se `Double` literais válidos: `0.0` . . . `1.2e5` `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="1db1f-115">Dada a expressão de matriz de qualquer tipo de elemento, uma `Int` expressão pode ser formada utilizando a [`Length`](xref:microsoft.quantum.core.length) função incorporada, com a expressão de matriz em anexo em parênteses, `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="1db1f-116">Por exemplo, se `a` está ligado a uma matriz, então é uma expressão `Length(a)` inteiro.</span><span class="sxs-lookup"><span data-stu-id="1db1f-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="1db1f-117">Se `b` for uma matriz de inteiros, `Int[][]` então é o número de `Length(b)` sub-matrizes em `b` , e é o número de `Length(b[1])` inteiros na segunda sub-matriz em `b` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="1db1f-118">Tendo em conta duas expressões numéricas do mesmo tipo, os operadores `+` `-` `*` binários, e `/` podem ser usados para formar uma nova expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="1db1f-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="1db1f-119">O tipo de nova expressão será o mesmo que os tipos de expressões constituintes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="1db1f-120">Tendo em conta duas expressões mais recentes, o operador binário `^` (potência) pode ser utilizado para formar uma nova expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="1db1f-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="1db1f-121">Da mesma forma, `^` pode ser usado com duas expressões duplas para formar uma nova expressão dupla.</span><span class="sxs-lookup"><span data-stu-id="1db1f-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="1db1f-122">Finalmente, `^` pode ser usado com um grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="1db1f-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="1db1f-123">Neste caso, o segundo parâmetro deve encaixar em 32 bits; caso contrário, será levantado um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1db1f-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="1db1f-124">Tendo em conta duas expressões inteiros ou grandes, uma nova expressão inteiro ou grande inteiro pode ser formada utilizando os `%` operadores (modulus), `&&&` (bitwise E), `|||` (bitwise OR) ou `^^^` (bitwise XOR).</span><span class="sxs-lookup"><span data-stu-id="1db1f-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="1db1f-125">Dada a expressão de um inteiro ou de um grande inteiro à esquerda, e uma expressão inteiro à direita, os `<<<` operadores (mudança à esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão da esquerda.</span><span class="sxs-lookup"><span data-stu-id="1db1f-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="1db1f-126">O segundo parâmetro (a quantidade de turno) para uma operação por turnos deve ser superior ou igual a zero; o comportamento para quantidades de turno negativas é indefinido.</span><span class="sxs-lookup"><span data-stu-id="1db1f-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="1db1f-127">O valor de deslocação para qualquer operação por turnos também deve caber em 32 bits; caso contrário, será levantado um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1db1f-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="1db1f-128">Se o número a ser deslocado for um número inteiro, então o valor do turno é `mod 64` interpretado; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="1db1f-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="1db1f-129">Tanto para os valores inteiros como para os grandes valores inteiros, as mudanças são aritmética.</span><span class="sxs-lookup"><span data-stu-id="1db1f-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="1db1f-130">Deslocar um valor negativo tanto à esquerda como à direita resultará num número negativo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="1db1f-131">Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1db1f-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="1db1f-132">A divisão de inteiros e o módulo inteiro seguem o mesmo comportamento para números negativos como C#.</span><span class="sxs-lookup"><span data-stu-id="1db1f-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="1db1f-133">Ou seja, `a % b` terá sempre o mesmo sinal `a` que, e sempre será `b * (a / b) + a % b` `a` igual.</span><span class="sxs-lookup"><span data-stu-id="1db1f-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="1db1f-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1db1f-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="1db1f-135">5</span><span class="sxs-lookup"><span data-stu-id="1db1f-135">5</span></span> | <span data-ttu-id="1db1f-136">2</span><span class="sxs-lookup"><span data-stu-id="1db1f-136">2</span></span> | <span data-ttu-id="1db1f-137">2</span><span class="sxs-lookup"><span data-stu-id="1db1f-137">2</span></span> | <span data-ttu-id="1db1f-138">1</span><span class="sxs-lookup"><span data-stu-id="1db1f-138">1</span></span>
 <span data-ttu-id="1db1f-139">5</span><span class="sxs-lookup"><span data-stu-id="1db1f-139">5</span></span> | <span data-ttu-id="1db1f-140">-2</span><span class="sxs-lookup"><span data-stu-id="1db1f-140">-2</span></span> | <span data-ttu-id="1db1f-141">-2</span><span class="sxs-lookup"><span data-stu-id="1db1f-141">-2</span></span> | <span data-ttu-id="1db1f-142">1</span><span class="sxs-lookup"><span data-stu-id="1db1f-142">1</span></span>
 <span data-ttu-id="1db1f-143">-5</span><span class="sxs-lookup"><span data-stu-id="1db1f-143">-5</span></span> | <span data-ttu-id="1db1f-144">2</span><span class="sxs-lookup"><span data-stu-id="1db1f-144">2</span></span> | <span data-ttu-id="1db1f-145">-2</span><span class="sxs-lookup"><span data-stu-id="1db1f-145">-2</span></span> | <span data-ttu-id="1db1f-146">-1</span><span class="sxs-lookup"><span data-stu-id="1db1f-146">-1</span></span>
 <span data-ttu-id="1db1f-147">-5</span><span class="sxs-lookup"><span data-stu-id="1db1f-147">-5</span></span> | <span data-ttu-id="1db1f-148">-2</span><span class="sxs-lookup"><span data-stu-id="1db1f-148">-2</span></span> | <span data-ttu-id="1db1f-149">2</span><span class="sxs-lookup"><span data-stu-id="1db1f-149">2</span></span> | <span data-ttu-id="1db1f-150">-1</span><span class="sxs-lookup"><span data-stu-id="1db1f-150">-1</span></span>

<span data-ttu-id="1db1f-151">A grande divisão de inteiros e o módulo funcionam da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="1db1f-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="1db1f-152">Dada qualquer expressão numérica, uma nova expressão pode ser formada usando o `-` operador unary.</span><span class="sxs-lookup"><span data-stu-id="1db1f-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="1db1f-153">A nova expressão será do mesmo tipo que a expressão constituinte.</span><span class="sxs-lookup"><span data-stu-id="1db1f-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="1db1f-154">Dada qualquer expressão completa ou grande, pode formar-se uma nova expressão do mesmo tipo utilizando o `~~~` operador unary (pequeno complemento).</span><span class="sxs-lookup"><span data-stu-id="1db1f-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="1db1f-155">Expressões booleanas</span><span class="sxs-lookup"><span data-stu-id="1db1f-155">Boolean Expressions</span></span>

<span data-ttu-id="1db1f-156">Os dois `Bool` valores literais são `true` `false` e.</span><span class="sxs-lookup"><span data-stu-id="1db1f-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="1db1f-157">Tendo em conta duas expressões do mesmo tipo primitivo, os `==` `!=` operadores binários podem ser utilizados para construir uma `Bool` expressão.</span><span class="sxs-lookup"><span data-stu-id="1db1f-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="1db1f-158">A expressão será verdadeira se as duas expressões forem iguais, e falsas se não.</span><span class="sxs-lookup"><span data-stu-id="1db1f-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="1db1f-159">Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores desembrulhados podem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="1db1f-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="1db1f-160">Por exemplo, utilizando o operador "desembrulhar" `!` (explicado em pormenor nos [tipos em Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="1db1f-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="1db1f-161">A comparação entre igualdade de `Qubit` valores é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.</span><span class="sxs-lookup"><span data-stu-id="1db1f-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="1db1f-162">O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="1db1f-163">A comparação entre a igualdade e `Double` os valores pode ser enganosa devido aos efeitos de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="1db1f-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="1db1f-164">Por exemplo, `49.0 * (1.0/49.0) != 1.0` . .</span><span class="sxs-lookup"><span data-stu-id="1db1f-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="1db1f-165">Tendo em conta duas expressões numéricas, os operadores binários `>` , e podem ser `<` `>=` `<=` usados para construir uma nova expressão booleana que é verdade se a primeira expressão for respectivamente maior do que, menos do que, maior ou igual a, ou inferior ou igual à segunda expressão.</span><span class="sxs-lookup"><span data-stu-id="1db1f-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="1db1f-166">Tendo em conta duas expressões booleanas, os `and` `or` operadores binários podem ser usados para construir uma nova expressão booleana que é verdade se ambas (resp. ou ambas) as duas expressões forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="1db1f-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="1db1f-167">Dada qualquer expressão booleana, o `not` operador unary pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.</span><span class="sxs-lookup"><span data-stu-id="1db1f-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="1db1f-168">Expressões de cordas</span><span class="sxs-lookup"><span data-stu-id="1db1f-168">String Expressions</span></span>

<span data-ttu-id="1db1f-169">Q# permite que as cordas sejam utilizadas na `fail` declaração (explicada no [Control Flow)](xref:microsoft.quantum.guide.controlflow#fail-statement)e na [`Message`](xref:microsoft.quantum.intrinsic.message) função padrão.</span><span class="sxs-lookup"><span data-stu-id="1db1f-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="1db1f-170">O comportamento específico deste último depende da utilização do simulador, mas normalmente escreve uma mensagem para a consola anfitriã quando é chamada durante um programa Q#.</span><span class="sxs-lookup"><span data-stu-id="1db1f-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="1db1f-171">As cordas em Q# são literais ou cordas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="1db1f-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="1db1f-172">As letras de corda são semelhantes às simples cordas literais na maioria das línguas: uma sequência de caracteres Unicode incluídos em citações duplas, `"` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="1db1f-173">Dentro de uma corda, o personagem de barra traseira `\` pode ser usado para escapar de um personagem de dupla citação, e para inserir uma nova linha como , um retorno de `\n` carruagem como , e uma guia `\r` como `\t` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="1db1f-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1db1f-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="1db1f-175">Cordas interpoladas</span><span class="sxs-lookup"><span data-stu-id="1db1f-175">Interpolated strings</span></span>

<span data-ttu-id="1db1f-176">A sintaxe Q# para interpolações de cordas é um subconjunto da sintaxe C#, mas resumimos aqui os pontos-chave que dizem respeito a Q#.</span><span class="sxs-lookup"><span data-stu-id="1db1f-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="1db1f-177">As principais distinções são discutidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="1db1f-178">Para identificar uma corda literal como uma corda interpolada, prepare-a com o `$` símbolo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="1db1f-179">Não se pode ter nenhum espaço em branco entre o `$` e o que começa uma corda `"` literal.</span><span class="sxs-lookup"><span data-stu-id="1db1f-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="1db1f-180">O seguinte é um exemplo básico usando a [`Message`](xref:microsoft.quantum.intrinsic.message) função para escrever o resultado de uma medição para a consola, ao lado de outras expressões Q#.</span><span class="sxs-lookup"><span data-stu-id="1db1f-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="1db1f-181">Qualquer expressão Q# válida pode aparecer numa corda interpolada.</span><span class="sxs-lookup"><span data-stu-id="1db1f-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="1db1f-182">Mais detalhes sobre a sintaxe C# podem ser encontrados em [*Cordas Interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="1db1f-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="1db1f-183">A distinção mais notável é que Q# não suporta cordas interpoladas verbatim (multi-line).</span><span class="sxs-lookup"><span data-stu-id="1db1f-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="1db1f-184">Expressões dentro de uma corda interpolada seguem a sintaxe Q#, não a sintaxe C#.</span><span class="sxs-lookup"><span data-stu-id="1db1f-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="1db1f-185">Expressões de alcance</span><span class="sxs-lookup"><span data-stu-id="1db1f-185">Range Expressions</span></span>

<span data-ttu-id="1db1f-186">Tendo em conta as três `Int` expressões `start` , e , é uma expressão de alcance cujo primeiro elemento é , o segundo `step` elemento é , o terceiro elemento é , `stop` `start .. step .. stop` `start` `start+step` `start+step+step` etc., até `stop` ser passado.</span><span class="sxs-lookup"><span data-stu-id="1db1f-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="1db1f-187">Um intervalo pode estar vazio se, por exemplo, `step` for positivo e `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="1db1f-188">O último elemento da gama será `stop` se a diferença entre e é um `start` `stop` múltiplo integral `step` de; ou seja, a gama é inclusiva em ambas as extremidades.</span><span class="sxs-lookup"><span data-stu-id="1db1f-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="1db1f-189">Tendo em conta `Int` duas expressões `start` `stop` e, `start .. stop` é uma expressão de alcance que é igual a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="1db1f-190">Note que o implícito `step` é +1 mesmo que `stop` seja `start` inferior; em tal caso, o intervalo está vazio.</span><span class="sxs-lookup"><span data-stu-id="1db1f-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="1db1f-191">Algumas gamas de exemplos são:</span><span class="sxs-lookup"><span data-stu-id="1db1f-191">Some example ranges are:</span></span>

- <span data-ttu-id="1db1f-192">`1..3`é o alcance 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="1db1f-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="1db1f-193">`2..2..5`é o alcance 2, 4.</span><span class="sxs-lookup"><span data-stu-id="1db1f-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="1db1f-194">`2..2..6`é o alcance 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="1db1f-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="1db1f-195">`6..-2..2`é o alcance 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="1db1f-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="1db1f-196">`2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="1db1f-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="1db1f-197">`2..6..7`é o alcance 2.</span><span class="sxs-lookup"><span data-stu-id="1db1f-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="1db1f-198">`2..2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="1db1f-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="1db1f-199">`1..-1..2`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="1db1f-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="1db1f-200">Expressões qubit</span><span class="sxs-lookup"><span data-stu-id="1db1f-200">Qubit Expressions</span></span>

<span data-ttu-id="1db1f-201">As `Qubit` únicas expressões são símbolos que estão ligados a `Qubit` valores ou elementos de `Qubit` matrizes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="1db1f-202">Não há `Qubit` literais.</span><span class="sxs-lookup"><span data-stu-id="1db1f-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="1db1f-203">Expressões Pauli</span><span class="sxs-lookup"><span data-stu-id="1db1f-203">Pauli Expressions</span></span>

<span data-ttu-id="1db1f-204">Os quatro `Pauli` valores são `PauliI` `PauliX` `PauliY` `PauliZ` `Pauli` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="1db1f-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="1db1f-205">Para além disso, as `Pauli` únicas expressões são símbolos que estão ligados a `Pauli` valores ou elementos de `Pauli` matrizes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="1db1f-206">Expressões de resultados</span><span class="sxs-lookup"><span data-stu-id="1db1f-206">Result Expressions</span></span>

<span data-ttu-id="1db1f-207">Os dois `Result` `One` valores, `Zero` e, são `Result` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="1db1f-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="1db1f-208">Para além disso, as `Result` únicas expressões são símbolos que estão ligados a `Result` valores ou elementos de `Result` matrizes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="1db1f-209">Em particular, note que não é o mesmo que `One` o inteiro , e não há conversão direta entre `1` eles.</span><span class="sxs-lookup"><span data-stu-id="1db1f-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="1db1f-210">O mesmo se aplica `Zero` `0` e. .</span><span class="sxs-lookup"><span data-stu-id="1db1f-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="1db1f-211">Expressões tuple</span><span class="sxs-lookup"><span data-stu-id="1db1f-211">Tuple Expressions</span></span>

<span data-ttu-id="1db1f-212">Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="1db1f-213">Por exemplo, `(1, One)` é uma `(Int, Result)` expressão.</span><span class="sxs-lookup"><span data-stu-id="1db1f-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="1db1f-214">Além das literais, as únicas expressões de tuple são símbolos que são obrigados a tuple valores, elementos de matrizes de tuple, e invocações callable que devolvem tuples.</span><span class="sxs-lookup"><span data-stu-id="1db1f-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="1db1f-215">Expressões de tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="1db1f-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="1db1f-216">Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="1db1f-217">Por exemplo, se `IntPair` for um tipo definido pelo utilizador baseado em , `(Int, Int)` então seria um literal válido desse `IntPair(2, 3)` tipo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="1db1f-218">Além das literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos de matrizes desse tipo, e invocações pôveis que devolvem esse tipo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="1db1f-219">Desembrulhar expressões</span><span class="sxs-lookup"><span data-stu-id="1db1f-219">Unwrap Expressions</span></span>

<span data-ttu-id="1db1f-220">Em Q#, o operador de desembrulhar é um ponto de exclamação em fuga `!` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="1db1f-221">Por exemplo, se `IntPair` for um tipo definido pelo utilizador com tipo `(Int, Int)` subjacente, e fosse uma `s` variável com `IntPair(2, 3)` valor, então `s!` seria `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="1db1f-222">Para os tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="1db1f-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="1db1f-223">o operador de desembrulhar pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="1db1f-224">Assim, se `WrappedPair` for um tipo definido pelo utilizador com tipo `IntPair` subjacente, e é uma `t` variável com `WrappedPair(IntPair(1,2))` valor, então `t!!` seria `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="1db1f-225">O `!` operador tem uma precedência mais elevada do que todos os outros operadores que não para a `[]` indexação e corte de matrizes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="1db1f-226">`!`e `[]` ligar posicionalmente; ou seja, `a[i]![3]` deve ser lido como : pegue no `((a[i])!)[3]` `i` 'th elemento de `a` , desembrulhá-lo, e, em seguida, obter o terceiro elemento do valor desembrulhado (que deve ser uma matriz).</span><span class="sxs-lookup"><span data-stu-id="1db1f-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="1db1f-227">A precedência do `!` operador tem um impacto que pode não ser óbvio.</span><span class="sxs-lookup"><span data-stu-id="1db1f-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="1db1f-228">Se uma função ou operação devolver um valor que seja desembrulhado, a função ou chamada de funcionamento deve ser fechada em parênteses para que o argumento se ligue à chamada e não ao desembrulho.</span><span class="sxs-lookup"><span data-stu-id="1db1f-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="1db1f-229">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1db1f-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="1db1f-230">Expressões de matriz</span><span class="sxs-lookup"><span data-stu-id="1db1f-230">Array Expressions</span></span>

<span data-ttu-id="1db1f-231">Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas `[` e `]` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="1db1f-232">Todos os elementos devem ser compatíveis com o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-232">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="1db1f-233">Tendo em conta duas matrizes do mesmo tipo, o operador binário `+` pode ser utilizado para formar uma nova matriz que é a concatenação das duas matrizes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="1db1f-234">Por exemplo, `[1,2,3] + [4,5,6]` é `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="1db1f-235">Criação de Matrizes</span><span class="sxs-lookup"><span data-stu-id="1db1f-235">Array Creation</span></span>

<span data-ttu-id="1db1f-236">Dado um tipo e uma `Int` expressão, o `new` operador pode ser utilizado para alocar uma nova matriz do tamanho dado.</span><span class="sxs-lookup"><span data-stu-id="1db1f-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="1db1f-237">Por exemplo, `new Int[i + 1]` atribuiria uma nova `Int` matriz com `i + 1` elementos.</span><span class="sxs-lookup"><span data-stu-id="1db1f-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="1db1f-238">Não são permitidos literais de matrizes `[]` vazias.</span><span class="sxs-lookup"><span data-stu-id="1db1f-238">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="1db1f-239">Em vez disso, a utilização `new ★[0]` , onde é reservado para um tipo `★` adequado, permite criar a matriz de comprimento zero desejada.</span><span class="sxs-lookup"><span data-stu-id="1db1f-239">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="1db1f-240">Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-240">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="1db1f-241">Na maioria dos casos, esta é uma variação de zero.</span><span class="sxs-lookup"><span data-stu-id="1db1f-241">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="1db1f-242">Para qubits e callables, que são referências a entidades, não existe um valor padrão razoável.</span><span class="sxs-lookup"><span data-stu-id="1db1f-242">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="1db1f-243">Assim, para estes tipos, o padrão é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1db1f-243">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="1db1f-244">Isto é semelhante a uma referência nula em línguas como C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="1db1f-244">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="1db1f-245">Os conjuntos que contenham qubits ou calcáveis devem ser corretamente inicializados com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança.</span><span class="sxs-lookup"><span data-stu-id="1db1f-245">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="1db1f-246">As rotinas de inicialização adequadas podem ser encontradas em <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="1db1f-246">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="1db1f-247">Os valores predefinidos para cada tipo são:</span><span class="sxs-lookup"><span data-stu-id="1db1f-247">The default values for each type are:</span></span>

<span data-ttu-id="1db1f-248">Tipo</span><span class="sxs-lookup"><span data-stu-id="1db1f-248">Type</span></span> | <span data-ttu-id="1db1f-249">Predefinição</span><span class="sxs-lookup"><span data-stu-id="1db1f-249">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="1db1f-250">_qubit inválido_</span><span class="sxs-lookup"><span data-stu-id="1db1f-250">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="1db1f-251">A gama vazia,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="1db1f-251">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="1db1f-252">_inválido callable_</span><span class="sxs-lookup"><span data-stu-id="1db1f-252">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="1db1f-253">Os tipos de tuple são elemento-por-elemento inicializados.</span><span class="sxs-lookup"><span data-stu-id="1db1f-253">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="1db1f-254">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="1db1f-254">Array Elements</span></span>

<span data-ttu-id="1db1f-255">Dada a expressão de matriz e uma `Int` expressão, uma nova expressão pode ser formada usando o operador de `[` elementos de matriz e `]` matriz.</span><span class="sxs-lookup"><span data-stu-id="1db1f-255">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="1db1f-256">A nova expressão será do mesmo tipo que o tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="1db1f-256">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="1db1f-257">Por exemplo, se `a` está ligado a uma matriz de `Double` s, então `a[4]` é uma `Double` expressão.</span><span class="sxs-lookup"><span data-stu-id="1db1f-257">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="1db1f-258">Se a expressão da matriz não for um identificador simples, deve ser fechada em parênteses para selecionar um elemento.</span><span class="sxs-lookup"><span data-stu-id="1db1f-258">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="1db1f-259">Por exemplo, se `a` e `b` forem ambos conjuntos de `Int` s, um elemento da concatenação seria expresso como:</span><span class="sxs-lookup"><span data-stu-id="1db1f-259">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="1db1f-260">Todos os arrays em Q# são baseados em zero.</span><span class="sxs-lookup"><span data-stu-id="1db1f-260">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="1db1f-261">Ou seja, o primeiro elemento de uma matriz `a` é `a[0]` sempre.</span><span class="sxs-lookup"><span data-stu-id="1db1f-261">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="1db1f-262">Fatias de Matriz</span><span class="sxs-lookup"><span data-stu-id="1db1f-262">Array Slices</span></span>

<span data-ttu-id="1db1f-263">Dada a expressão de matriz e uma `Range` expressão, uma nova expressão pode ser formada usando o operador de `[` fatias de `]` matriz e matriz.</span><span class="sxs-lookup"><span data-stu-id="1db1f-263">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="1db1f-264">A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range` , na ordem definida pelo `Range` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-264">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="1db1f-265">Por exemplo, se `a` estiver ligado a um conjunto de `Double` s, então `a[3..-1..0]` é uma expressão que contém os `Double[]` primeiros quatro elementos de `a` mas na ordem inversa como aparecem em `a` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-265">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="1db1f-266">Se a `Range` fatia estiver vazia, a fatia de matriz resultante terá um comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="1db1f-266">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="1db1f-267">Tal como acontece com os elementos de matriz de referência, se a expressão da matriz não for um simples identificador, deve ser fechada parênteses para cortar.</span><span class="sxs-lookup"><span data-stu-id="1db1f-267">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="1db1f-268">Se `a` e forem ambos `b` conjuntos de `Int` s, uma fatia da concatenação seria expressa como:</span><span class="sxs-lookup"><span data-stu-id="1db1f-268">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="1db1f-269">Valores inferidos de início/fim</span><span class="sxs-lookup"><span data-stu-id="1db1f-269">Inferred start/end values</span></span>

<span data-ttu-id="1db1f-270">Começando com o nosso lançamento 0.8, apoiamos expressões contextuais para corte de alcance.</span><span class="sxs-lookup"><span data-stu-id="1db1f-270">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="1db1f-271">Em especial, os valores de arranque e de fim de gama podem ser omitidos no contexto de uma expressão de corte de gama.</span><span class="sxs-lookup"><span data-stu-id="1db1f-271">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="1db1f-272">Nesse caso, o compilador aplicará as seguintes regras para inferir os delimiters previstos para o intervalo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-272">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="1db1f-273">Por exemplo, se o valor inicial da gama for omitido, então o valor inicial inferido</span><span class="sxs-lookup"><span data-stu-id="1db1f-273">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="1db1f-274">é zero se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="1db1f-274">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="1db1f-275">é o comprimento da matriz fatiada menos um se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-275">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="1db1f-276">Se o valor final da gama for omitido, então o valor final inferido</span><span class="sxs-lookup"><span data-stu-id="1db1f-276">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="1db1f-277">é o comprimento da matriz fatiada menos um se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="1db1f-277">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="1db1f-278">é zero se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-278">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="1db1f-279">Expressões de cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="1db1f-279">Copy-and-Update Expressions</span></span>

<span data-ttu-id="1db1f-280">Uma vez que todos os tipos Q# são tipos de valor — com os qubits a assumirem um papel um pouco especial — formalmente é criada uma "cópia" quando um valor está ligado a um símbolo, ou quando um símbolo é recuperado.</span><span class="sxs-lookup"><span data-stu-id="1db1f-280">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="1db1f-281">Ou seja, o comportamento de Q# é o mesmo que se uma cópia fosse criada numa missão.</span><span class="sxs-lookup"><span data-stu-id="1db1f-281">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="1db1f-282">Naturalmente, na prática, apenas as peças relevantes são recriadas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="1db1f-282">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="1db1f-283">Isto inclui também matrizes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-283">This in particular also includes arrays.</span></span>
<span data-ttu-id="1db1f-284">Em particular, não é possível atualizar os itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="1db1f-284">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="1db1f-285">Modificar uma matriz existente requer uma alavancagem de um mecanismo *de cópia e atualização.*</span><span class="sxs-lookup"><span data-stu-id="1db1f-285">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="1db1f-286">Novas matrizes podem ser criadas a partir das existentes através de expressões *de cópia e atualização.*</span><span class="sxs-lookup"><span data-stu-id="1db1f-286">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="1db1f-287">Uma expressão de cópia e atualização é uma expressão do `expression1 w/ expression2 <- expression3` formulário, onde `expression1` tem de ser do tipo para algum tipo `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-287">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="1db1f-288">O segundo `expression2` define os índices dos elementos(s) para modificar em comparação com a matriz `expression1` e tem de ser de tipo ou de tipo `Int` `Range` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-288">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="1db1f-289">Se `expression2` for do `Int` tipo, tem de ser do `expression3` `T` tipo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-289">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="1db1f-290">Se `expression2` for do `Range` tipo, tem de ser do `expression3` `T[]` tipo.</span><span class="sxs-lookup"><span data-stu-id="1db1f-290">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="1db1f-291">Uma expressão de cópia e atualização `arr w/ idx <- value` constrói uma nova matriz com todos os elementos definidos para o elemento correspondente em , exceto os `arr` elementos em , que são `idx` definidos para o(s) em `value` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-291">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="1db1f-292">Por exemplo, se `arr` contiver uma `[0,1,2,3]` matriz, então</span><span class="sxs-lookup"><span data-stu-id="1db1f-292">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="1db1f-293">`arr w/ 0 <- 10`é a matriz `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-293">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="1db1f-294">`arr w/ 2 <- 10`é a matriz `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-294">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="1db1f-295">`arr w/ 0..2..3 <- [10,12]`é a matriz `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-295">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="1db1f-296">Expressões de cópia e atualização para itens nomeados</span><span class="sxs-lookup"><span data-stu-id="1db1f-296">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="1db1f-297">Expressões semelhantes existem para itens nomeados em tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="1db1f-297">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="1db1f-298">Considere, por exemplo, o tipo</span><span class="sxs-lookup"><span data-stu-id="1db1f-298">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="1db1f-299">Se `c` contiver o valor do `Complex(1., -1.)` tipo, então `c w/ Re <- 0.` é uma expressão do tipo que avalia `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-299">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="1db1f-300">Matrizes irregulares</span><span class="sxs-lookup"><span data-stu-id="1db1f-300">Jagged Arrays</span></span>

<span data-ttu-id="1db1f-301">Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes.</span><span class="sxs-lookup"><span data-stu-id="1db1f-301">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="1db1f-302">Os elementos de uma matriz irregular podem ser de diferentes tamanhos.</span><span class="sxs-lookup"><span data-stu-id="1db1f-302">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="1db1f-303">O exemplo a seguir mostra como declarar e inicializar uma matriz irregular que representa uma tabela de multiplicação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-303">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="1db1f-304">Matrizes de callables</span><span class="sxs-lookup"><span data-stu-id="1db1f-304">Arrays of callables</span></span> 

<span data-ttu-id="1db1f-305">Note que mais detalhes sobre tipos de chamadas podem ser encontrados abaixo, bem como na página seguinte, [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="1db1f-305">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="1db1f-306">Se o tipo de elemento comum for um tipo de funcionamento ou função, todos os elementos devem ter os mesmos tipos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="1db1f-306">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="1db1f-307">O tipo de elemento da matriz irá suportar quaisquer funtores que sejam suportados por todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="1db1f-307">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="1db1f-308">Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="1db1f-308">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="1db1f-309">`[Op1, Op2]`é uma série de `(Qubit[] => Unit)` operações.</span><span class="sxs-lookup"><span data-stu-id="1db1f-309">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="1db1f-310">`[Op1, Op3]`é uma série de `(Qubit[] => Unit is Adj)` operações.</span><span class="sxs-lookup"><span data-stu-id="1db1f-310">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="1db1f-311">`[Op2, Op3]`é uma série de `(Qubit[] => Unit is Ctl)` operações.</span><span class="sxs-lookup"><span data-stu-id="1db1f-311">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="1db1f-312">No entanto, embora `(Qubit[] => Unit is Adj)` as `(Qubit[] => Unit is Ctl)` operações tenham o tipo de base comum `(Qubit[] => Unit)` de, note-se que as matrizes destes operadores não partilham um tipo de base comum. *of*</span><span class="sxs-lookup"><span data-stu-id="1db1f-312">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="1db1f-313">Por exemplo, `[[Op1], [Op2]]` atualmente levantaria um erro porque está a tentar criar uma matriz dos tipos de matrizes incompatíveis `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-313">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="1db1f-314">Expressões Condicionais</span><span class="sxs-lookup"><span data-stu-id="1db1f-314">Conditional Expressions</span></span>

<span data-ttu-id="1db1f-315">Tendo em conta duas outras expressões do mesmo tipo e uma expressão booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação `?` e a barra vertical `|` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-315">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="1db1f-316">Por exemplo, `a==b ? c | d` . .</span><span class="sxs-lookup"><span data-stu-id="1db1f-316">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="1db1f-317">Neste exemplo, o valor da expressão condicional será `c` se for verdade e se for `a==b` `d` falso.</span><span class="sxs-lookup"><span data-stu-id="1db1f-317">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="1db1f-318">Expressões condicionais com callables</span><span class="sxs-lookup"><span data-stu-id="1db1f-318">Conditional expressions with callables</span></span>

<span data-ttu-id="1db1f-319">As duas expressões podem avaliar operações que tenham as mesmas entradas e saídas, mas suportam diferentes functors.</span><span class="sxs-lookup"><span data-stu-id="1db1f-319">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="1db1f-320">Neste caso, o tipo de expressão condicional é uma operação com as entradas e saídas que suportam quaisquer funtores apoiados por ambas as expressões.</span><span class="sxs-lookup"><span data-stu-id="1db1f-320">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="1db1f-321">Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="1db1f-321">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="1db1f-322">`flag ? Op1 | Op2`é uma `(Qubit[] => Unit)` operação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-322">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="1db1f-323">`flag ? Op1 | Op3`é uma `(Qubit[] => Unit is Adj)` operação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-323">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="1db1f-324">`flag ? Op2 | Op3`é uma `(Qubit[] => Unit is Ctl)` operação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-324">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="1db1f-325">Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de funcionamento, essa chamada só será efetuada se esse resultado for o valor da chamada.</span><span class="sxs-lookup"><span data-stu-id="1db1f-325">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="1db1f-326">Por exemplo, no caso `a==b ? C(qs) | D(qs)` , se `a==b` for verdade, a `C` operação será invocada, e se for falsa, só `D` será invocada.</span><span class="sxs-lookup"><span data-stu-id="1db1f-326">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="1db1f-327">Isto é semelhante ao curto-circuito em outras línguas.</span><span class="sxs-lookup"><span data-stu-id="1db1f-327">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="1db1f-328">Expressões calláveis</span><span class="sxs-lookup"><span data-stu-id="1db1f-328">Callable Expressions</span></span>

<span data-ttu-id="1db1f-329">Um literal chamado é o nome de uma operação ou função definida no âmbito de compilação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-329">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="1db1f-330">Por exemplo, `X` é uma operação literal que se refere à operação padrão da `X` biblioteca, e é uma `Message` função literal que se refere à função de biblioteca `Message` padrão.</span><span class="sxs-lookup"><span data-stu-id="1db1f-330">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="1db1f-331">Se uma operação suporta o `Adjoint` functor, então `Adjoint op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-331">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="1db1f-332">Da mesma forma, se a operação suporta o `Controlled` functor, então `Controlled op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-332">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="1db1f-333">Os tipos destas expressões são especificados nas [especializações da operação Call](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="1db1f-333">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="1db1f-334">Os functores `Adjoint` (e `Controlled` ) ligam-se mais estreitamente do que todos os outros operadores, com exceção do operador de desembrulhar `!` e da indexação da matriz com []».</span><span class="sxs-lookup"><span data-stu-id="1db1f-334">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="1db1f-335">Assim, todos são legais, assumindo que as operações suportam os funtores utilizados:</span><span class="sxs-lookup"><span data-stu-id="1db1f-335">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="1db1f-336">Expressões de caloisos por tipo parametrizadas</span><span class="sxs-lookup"><span data-stu-id="1db1f-336">Type-parameterized callable expressions</span></span>

<span data-ttu-id="1db1f-337">Um literal chamado pode ser usado como um valor, por exemplo, para atribuir a uma variável ou para passar para outra chamada.</span><span class="sxs-lookup"><span data-stu-id="1db1f-337">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="1db1f-338">Neste caso, se a chamada tiver [parâmetros de tipo,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)devem ser fornecidos como parte do valor de chamada.</span><span class="sxs-lookup"><span data-stu-id="1db1f-338">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="1db1f-339">Um valor calável não pode ter parâmetros de tipo não especificados.</span><span class="sxs-lookup"><span data-stu-id="1db1f-339">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="1db1f-340">Por exemplo, se `Fun` for uma função com `'T1->Unit` assinatura:</span><span class="sxs-lookup"><span data-stu-id="1db1f-340">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="1db1f-341">Expressões de invocação callable</span><span class="sxs-lookup"><span data-stu-id="1db1f-341">Callable Invocation Expressions</span></span>

<span data-ttu-id="1db1f-342">Dada uma expressão callable (operação ou função) e uma expressão tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada por anexar a expressão de tuple à expressão callable.</span><span class="sxs-lookup"><span data-stu-id="1db1f-342">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="1db1f-343">O tipo de expressão de invocação é o tipo de saída da assinatura do callable.</span><span class="sxs-lookup"><span data-stu-id="1db1f-343">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="1db1f-344">Por exemplo, se `Op` for uma operação com `((Int, Qubit) => Double)` assinatura, é uma expressão do tipo `Op(3, qubit1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-344">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="1db1f-345">Da mesma forma, se `Sin` for uma função com `(Double -> Double)` assinatura, é uma expressão do tipo `Sin(0.1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="1db1f-345">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="1db1f-346">Finalmente, se `Builder` é uma função com `(Int -> (Int -> Int))` assinatura, então `Builder(3)` é uma função de Into to Int.</span><span class="sxs-lookup"><span data-stu-id="1db1f-346">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="1db1f-347">Invocar o resultado de uma expressão de valor callable requer um par extra de parênteses em torno da expressão callable.</span><span class="sxs-lookup"><span data-stu-id="1db1f-347">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="1db1f-348">Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:</span><span class="sxs-lookup"><span data-stu-id="1db1f-348">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="1db1f-349">Ao invocar uma chamada [tipo-parametrizada,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) os parâmetros do tipo real podem ser especificados dentro dos suportes angulares `<` e após a expressão `>` callable.</span><span class="sxs-lookup"><span data-stu-id="1db1f-349">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="1db1f-350">Isto é geralmente desnecessário, uma vez que o compilador Q# infere os tipos reais.</span><span class="sxs-lookup"><span data-stu-id="1db1f-350">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="1db1f-351">No entanto, *é* necessário para [a aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se um argumento porontose de tipo não for especificado.</span><span class="sxs-lookup"><span data-stu-id="1db1f-351">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="1db1f-352">Também é por vezes útil ao passar operações com diferentes suportes de functor para um callable.</span><span class="sxs-lookup"><span data-stu-id="1db1f-352">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="1db1f-353">Por exemplo, se `Func` tiver assinatura , e ter assinatura , e tiver assinatura , para invocar `('T1, 'T2, 'T1) -> 'T2` como primeiro `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` `Op1` argumento, como o `Op2` segundo, e como o `Op3` terceiro:</span><span class="sxs-lookup"><span data-stu-id="1db1f-353">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="1db1f-354">A especificação do tipo é necessária porque `Op3` e `Op1` tem diferentes tipos, de modo que o compilador tratará isto como ambíguo sem a especificação.</span><span class="sxs-lookup"><span data-stu-id="1db1f-354">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="1db1f-355">Precedência do operador</span><span class="sxs-lookup"><span data-stu-id="1db1f-355">Operator Precedence</span></span>

<span data-ttu-id="1db1f-356">Todos os operadores binários são associados à direita, `^` exceto.</span><span class="sxs-lookup"><span data-stu-id="1db1f-356">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="1db1f-357">Os suportes `[` `]` e, para cortar e indexar a matriz, ligam-se perante qualquer operador.</span><span class="sxs-lookup"><span data-stu-id="1db1f-357">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="1db1f-358">Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.</span><span class="sxs-lookup"><span data-stu-id="1db1f-358">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="1db1f-359">Os parênteses para a invocação de funcionamento e função também se ligam perante qualquer operador, mas após a indexação de matrizes e funtores.</span><span class="sxs-lookup"><span data-stu-id="1db1f-359">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="1db1f-360">Operadores por ordem de precedência, da mais alta para a mais baixa:</span><span class="sxs-lookup"><span data-stu-id="1db1f-360">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="1db1f-361">Operador</span><span class="sxs-lookup"><span data-stu-id="1db1f-361">Operator</span></span> | <span data-ttu-id="1db1f-362">Arity</span><span class="sxs-lookup"><span data-stu-id="1db1f-362">Arity</span></span> | <span data-ttu-id="1db1f-363">Description</span><span class="sxs-lookup"><span data-stu-id="1db1f-363">Description</span></span> | <span data-ttu-id="1db1f-364">Tipos operand</span><span class="sxs-lookup"><span data-stu-id="1db1f-364">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="1db1f-365">trailing`!`</span><span class="sxs-lookup"><span data-stu-id="1db1f-365">trailing `!`</span></span> | <span data-ttu-id="1db1f-366">Unária</span><span class="sxs-lookup"><span data-stu-id="1db1f-366">Unary</span></span> | <span data-ttu-id="1db1f-367">Desembrulhar</span><span class="sxs-lookup"><span data-stu-id="1db1f-367">Unwrap</span></span> | <span data-ttu-id="1db1f-368">Qualquer tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="1db1f-368">Any user-defined type</span></span>
 <span data-ttu-id="1db1f-369">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="1db1f-369">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="1db1f-370">Unária</span><span class="sxs-lookup"><span data-stu-id="1db1f-370">Unary</span></span> | <span data-ttu-id="1db1f-371">Numérico negativo, complemento bitwise, negação lógica</span><span class="sxs-lookup"><span data-stu-id="1db1f-371">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="1db1f-372">`Int`, `BigInt` ou `Double` `-` para, ou para `Int` `BigInt` `~~~` , `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="1db1f-372">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="1db1f-373">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-373">Binary</span></span> | <span data-ttu-id="1db1f-374">Poder inteiro</span><span class="sxs-lookup"><span data-stu-id="1db1f-374">Integer power</span></span> | <span data-ttu-id="1db1f-375">`Int`ou `BigInt` para a base, para o `Int` expoente</span><span class="sxs-lookup"><span data-stu-id="1db1f-375">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="1db1f-376">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="1db1f-376">`/`, `*`, `%`</span></span> | <span data-ttu-id="1db1f-377">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-377">Binary</span></span> | <span data-ttu-id="1db1f-378">Divisão, multiplicação, módulo inteiro</span><span class="sxs-lookup"><span data-stu-id="1db1f-378">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="1db1f-379">`Int`, `BigInt` ou `Double` para `/` `*` e, ou `Int` `BigInt` para`%`</span><span class="sxs-lookup"><span data-stu-id="1db1f-379">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="1db1f-380">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="1db1f-380">`+`, `-`</span></span> | <span data-ttu-id="1db1f-381">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-381">Binary</span></span> | <span data-ttu-id="1db1f-382">Adição ou cadeia e concatenação de matriz, subtração</span><span class="sxs-lookup"><span data-stu-id="1db1f-382">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="1db1f-383">`Int`, `BigInt` ou `Double` , adicionalmente ou qualquer tipo de matriz `String` para`+`</span><span class="sxs-lookup"><span data-stu-id="1db1f-383">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="1db1f-384">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="1db1f-384">`<<<`, `>>>`</span></span> | <span data-ttu-id="1db1f-385">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-385">Binary</span></span> | <span data-ttu-id="1db1f-386">Turno da esquerda, turno da direita</span><span class="sxs-lookup"><span data-stu-id="1db1f-386">Left shift, right shift</span></span> | <span data-ttu-id="1db1f-387">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1db1f-387">`Int` or `BigInt`</span></span>
 <span data-ttu-id="1db1f-388">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="1db1f-388">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="1db1f-389">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-389">Binary</span></span> | <span data-ttu-id="1db1f-390">Comparações menos do que, menos ou iguais, maiores do que, maiores do que iguais</span><span class="sxs-lookup"><span data-stu-id="1db1f-390">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="1db1f-391">`Int`, `BigInt` ou`Double`</span><span class="sxs-lookup"><span data-stu-id="1db1f-391">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="1db1f-392">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="1db1f-392">`==`, `!=`</span></span> | <span data-ttu-id="1db1f-393">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-393">Binary</span></span> | <span data-ttu-id="1db1f-394">comparações iguais e não iguais</span><span class="sxs-lookup"><span data-stu-id="1db1f-394">equal, not-equal comparisons</span></span> | <span data-ttu-id="1db1f-395">qualquer tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="1db1f-395">any primitive type</span></span>
 `&&&` | <span data-ttu-id="1db1f-396">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-396">Binary</span></span> | <span data-ttu-id="1db1f-397">Bitwise E</span><span class="sxs-lookup"><span data-stu-id="1db1f-397">Bitwise AND</span></span> | <span data-ttu-id="1db1f-398">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1db1f-398">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="1db1f-399">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-399">Binary</span></span> | <span data-ttu-id="1db1f-400">Bitwise XOR</span><span class="sxs-lookup"><span data-stu-id="1db1f-400">Bitwise XOR</span></span> | <span data-ttu-id="1db1f-401">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1db1f-401">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="1db1f-402">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-402">Binary</span></span> | <span data-ttu-id="1db1f-403">Bitwise OR</span><span class="sxs-lookup"><span data-stu-id="1db1f-403">Bitwise OR</span></span> | <span data-ttu-id="1db1f-404">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1db1f-404">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="1db1f-405">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-405">Binary</span></span> | <span data-ttu-id="1db1f-406">AND lógico</span><span class="sxs-lookup"><span data-stu-id="1db1f-406">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="1db1f-407">Binário</span><span class="sxs-lookup"><span data-stu-id="1db1f-407">Binary</span></span> | <span data-ttu-id="1db1f-408">OR lógico</span><span class="sxs-lookup"><span data-stu-id="1db1f-408">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="1db1f-409">Binário/Ternário</span><span class="sxs-lookup"><span data-stu-id="1db1f-409">Binary/Ternary</span></span> | <span data-ttu-id="1db1f-410">Operador de gama</span><span class="sxs-lookup"><span data-stu-id="1db1f-410">Range operator</span></span> | `Int`
 <span data-ttu-id="1db1f-411">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="1db1f-411">`?` `|`</span></span> | <span data-ttu-id="1db1f-412">Ternário</span><span class="sxs-lookup"><span data-stu-id="1db1f-412">Ternary</span></span> | <span data-ttu-id="1db1f-413">Condicional</span><span class="sxs-lookup"><span data-stu-id="1db1f-413">Conditional</span></span> | <span data-ttu-id="1db1f-414">`Bool`para o lado esquerdo</span><span class="sxs-lookup"><span data-stu-id="1db1f-414">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="1db1f-415">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="1db1f-415">`w/` `<-`</span></span> | <span data-ttu-id="1db1f-416">Ternário</span><span class="sxs-lookup"><span data-stu-id="1db1f-416">Ternary</span></span> | <span data-ttu-id="1db1f-417">Cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="1db1f-417">Copy-and-update</span></span> | <span data-ttu-id="1db1f-418">ver [expressões de cópia e atualização](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="1db1f-418">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="1db1f-419">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="1db1f-419">Next steps</span></span>

<span data-ttu-id="1db1f-420">Agora que pode trabalhar com expressões em Q#, pode dirigir-se a [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions) para aprender a definir e chamar operações e funções.</span><span class="sxs-lookup"><span data-stu-id="1db1f-420">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
