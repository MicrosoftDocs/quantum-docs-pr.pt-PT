---
title: 'Expressãos tipo em Q #'
description: Entenda como especificar, referenciar e combinar constantes, variáveis, operadores, operações e funções como expressões em Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630003"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="a5890-103">Expressãos tipo em Q #</span><span class="sxs-lookup"><span data-stu-id="a5890-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="a5890-104">Expressões numéricas</span><span class="sxs-lookup"><span data-stu-id="a5890-104">Numeric Expressions</span></span>

<span data-ttu-id="a5890-105">Expressões numéricas são expressões do `Int` `BigInt` tipo, ou `Double` .</span><span class="sxs-lookup"><span data-stu-id="a5890-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="a5890-106">Ou seja, ou são números inteiros ou de pontos flutuantes.</span><span class="sxs-lookup"><span data-stu-id="a5890-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="a5890-107">`Int`literais em Q# são escritos simplesmente como uma sequência de dígitos.</span><span class="sxs-lookup"><span data-stu-id="a5890-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="a5890-108">Os inteiros hexadecimais e binários são suportados com um `0x` `0b` e prefixo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a5890-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="a5890-109">`BigInt`literais em Q# são escritos com um rasto `l` ou `L` sufixo.</span><span class="sxs-lookup"><span data-stu-id="a5890-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="a5890-110">Os grandes inteiros hexadecimais são suportados com um prefixo "0x".</span><span class="sxs-lookup"><span data-stu-id="a5890-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="a5890-111">Assim, todas são utilizações válidas de `BigInt` literais:</span><span class="sxs-lookup"><span data-stu-id="a5890-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="a5890-112">`Double`literais em Q# são números de ponto flutuante escritos usando dígitos decimais.</span><span class="sxs-lookup"><span data-stu-id="a5890-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="a5890-113">Podem ser escritos com um ponto decimal, `.` e/ou uma parte exponencial indicada com 'e' ou 'E' (após o qual apenas são válidos um possível sinal negativo e dígitos decimais).</span><span class="sxs-lookup"><span data-stu-id="a5890-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="a5890-114">Seguem-se `Double` literais válidos: `0.0` . . . `1.2e5` `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="a5890-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="a5890-115">Dada a expressão de matriz de qualquer tipo de elemento, uma `Int` expressão pode ser formada utilizando a [`Length`](xref:microsoft.quantum.core.length) função incorporada, com a expressão de matriz em anexo em parênteses, `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="a5890-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="a5890-116">Por exemplo, se `a` está ligado a uma matriz, então é uma expressão `Length(a)` inteiro.</span><span class="sxs-lookup"><span data-stu-id="a5890-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="a5890-117">Se `b` for uma matriz de inteiros, `Int[][]` então é o número de `Length(b)` sub-matrizes em `b` , e é o número de `Length(b[1])` inteiros na segunda sub-matriz em `b` .</span><span class="sxs-lookup"><span data-stu-id="a5890-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="a5890-118">Tendo em conta duas expressões numéricas do mesmo tipo, os operadores `+` `-` `*` binários, e `/` podem ser usados para formar uma nova expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="a5890-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="a5890-119">O tipo de nova expressão será o mesmo que os tipos de expressões constituintes.</span><span class="sxs-lookup"><span data-stu-id="a5890-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="a5890-120">Tendo em conta duas expressões mais recentes, o operador binário `^` (potência) pode ser utilizado para formar uma nova expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="a5890-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="a5890-121">Da mesma forma, `^` pode ser usado com duas expressões duplas para formar uma nova expressão dupla.</span><span class="sxs-lookup"><span data-stu-id="a5890-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="a5890-122">Finalmente, `^` pode ser usado com um grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="a5890-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="a5890-123">Neste caso, o segundo parâmetro deve encaixar em 32 bits; caso contrário, será levantado um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a5890-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="a5890-124">Tendo em conta duas expressões inteiros ou grandes, uma nova expressão inteiro ou grande inteiro pode ser formada utilizando os `%` operadores (modulus), `&&&` (bitwise E), `|||` (bitwise OR) ou `^^^` (bitwise XOR).</span><span class="sxs-lookup"><span data-stu-id="a5890-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="a5890-125">Dada a expressão de um inteiro ou de um grande inteiro à esquerda, e uma expressão inteiro à direita, os `<<<` operadores (mudança à esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão da esquerda.</span><span class="sxs-lookup"><span data-stu-id="a5890-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="a5890-126">O segundo parâmetro (a quantidade de turno) para uma operação por turnos deve ser superior ou igual a zero; o comportamento para quantidades de turno negativas é indefinido.</span><span class="sxs-lookup"><span data-stu-id="a5890-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="a5890-127">O valor de deslocação para qualquer operação por turnos também deve caber em 32 bits; caso contrário, será levantado um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a5890-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="a5890-128">Se o número a ser deslocado for um número inteiro, então o valor do turno é `mod 64` interpretado; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="a5890-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="a5890-129">Tanto para os valores inteiros como para os grandes valores inteiros, as mudanças são aritmética.</span><span class="sxs-lookup"><span data-stu-id="a5890-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="a5890-130">Deslocar um valor negativo tanto à esquerda como à direita resultará num número negativo.</span><span class="sxs-lookup"><span data-stu-id="a5890-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="a5890-131">Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a5890-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="a5890-132">A divisão de inteiros e o módulo inteiro seguem o mesmo comportamento para números negativos como C#.</span><span class="sxs-lookup"><span data-stu-id="a5890-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="a5890-133">Ou seja, `a % b` terá sempre o mesmo sinal `a` que, e sempre será `b * (a / b) + a % b` `a` igual.</span><span class="sxs-lookup"><span data-stu-id="a5890-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="a5890-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a5890-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="a5890-135">5</span><span class="sxs-lookup"><span data-stu-id="a5890-135">5</span></span> | <span data-ttu-id="a5890-136">2</span><span class="sxs-lookup"><span data-stu-id="a5890-136">2</span></span> | <span data-ttu-id="a5890-137">2</span><span class="sxs-lookup"><span data-stu-id="a5890-137">2</span></span> | <span data-ttu-id="a5890-138">1</span><span class="sxs-lookup"><span data-stu-id="a5890-138">1</span></span>
 <span data-ttu-id="a5890-139">5</span><span class="sxs-lookup"><span data-stu-id="a5890-139">5</span></span> | <span data-ttu-id="a5890-140">-2</span><span class="sxs-lookup"><span data-stu-id="a5890-140">-2</span></span> | <span data-ttu-id="a5890-141">-2</span><span class="sxs-lookup"><span data-stu-id="a5890-141">-2</span></span> | <span data-ttu-id="a5890-142">1</span><span class="sxs-lookup"><span data-stu-id="a5890-142">1</span></span>
 <span data-ttu-id="a5890-143">-5</span><span class="sxs-lookup"><span data-stu-id="a5890-143">-5</span></span> | <span data-ttu-id="a5890-144">2</span><span class="sxs-lookup"><span data-stu-id="a5890-144">2</span></span> | <span data-ttu-id="a5890-145">-2</span><span class="sxs-lookup"><span data-stu-id="a5890-145">-2</span></span> | <span data-ttu-id="a5890-146">-1</span><span class="sxs-lookup"><span data-stu-id="a5890-146">-1</span></span>
 <span data-ttu-id="a5890-147">-5</span><span class="sxs-lookup"><span data-stu-id="a5890-147">-5</span></span> | <span data-ttu-id="a5890-148">-2</span><span class="sxs-lookup"><span data-stu-id="a5890-148">-2</span></span> | <span data-ttu-id="a5890-149">2</span><span class="sxs-lookup"><span data-stu-id="a5890-149">2</span></span> | <span data-ttu-id="a5890-150">-1</span><span class="sxs-lookup"><span data-stu-id="a5890-150">-1</span></span>

<span data-ttu-id="a5890-151">A grande divisão de inteiros e o módulo funcionam da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="a5890-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="a5890-152">Dada qualquer expressão numérica, uma nova expressão pode ser formada usando o `-` operador unary.</span><span class="sxs-lookup"><span data-stu-id="a5890-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="a5890-153">A nova expressão será do mesmo tipo que a expressão constituinte.</span><span class="sxs-lookup"><span data-stu-id="a5890-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="a5890-154">Dada qualquer expressão completa ou grande, pode formar-se uma nova expressão do mesmo tipo utilizando o `~~~` operador unary (pequeno complemento).</span><span class="sxs-lookup"><span data-stu-id="a5890-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="a5890-155">Expressões booleanas</span><span class="sxs-lookup"><span data-stu-id="a5890-155">Boolean Expressions</span></span>

<span data-ttu-id="a5890-156">Os dois `Bool` valores literais são `true` `false` e.</span><span class="sxs-lookup"><span data-stu-id="a5890-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="a5890-157">Tendo em conta duas expressões do mesmo tipo primitivo, os `==` `!=` operadores binários podem ser utilizados para construir uma `Bool` expressão.</span><span class="sxs-lookup"><span data-stu-id="a5890-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="a5890-158">A expressão será verdadeira se as duas expressões forem iguais, e falsas se não.</span><span class="sxs-lookup"><span data-stu-id="a5890-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="a5890-159">Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores desembrulhados podem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="a5890-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="a5890-160">Por exemplo, utilizando o operador "desembrulhar" `!` (explicado em pormenor nos [tipos em Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="a5890-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="a5890-161">A comparação entre igualdade de `Qubit` valores é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.</span><span class="sxs-lookup"><span data-stu-id="a5890-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="a5890-162">O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.</span><span class="sxs-lookup"><span data-stu-id="a5890-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="a5890-163">A comparação entre a igualdade e `Double` os valores pode ser enganosa devido aos efeitos de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="a5890-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="a5890-164">Por exemplo, `49.0 * (1.0/49.0) != 1.0` . .</span><span class="sxs-lookup"><span data-stu-id="a5890-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="a5890-165">Tendo em conta duas expressões numéricas, os operadores binários `>` , e podem ser `<` `>=` `<=` usados para construir uma nova expressão booleana que é verdade se a primeira expressão for respectivamente maior do que, menos do que, maior ou igual a, ou inferior ou igual à segunda expressão.</span><span class="sxs-lookup"><span data-stu-id="a5890-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="a5890-166">Tendo em conta duas expressões booleanas, os `and` `or` operadores binários podem ser usados para construir uma nova expressão booleana que é verdade se ambas (resp. ou ambas) as duas expressões forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="a5890-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="a5890-167">Dada qualquer expressão booleana, o `not` operador unary pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.</span><span class="sxs-lookup"><span data-stu-id="a5890-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="a5890-168">Expressões de cordas</span><span class="sxs-lookup"><span data-stu-id="a5890-168">String Expressions</span></span>

<span data-ttu-id="a5890-169">Q# permite que as cordas sejam utilizadas na `fail` declaração (explicada no [Control Flow)](xref:microsoft.quantum.guide.controlflow#fail-statement)e na [`Message`](xref:microsoft.quantum.intrinsic.message) função padrão.</span><span class="sxs-lookup"><span data-stu-id="a5890-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="a5890-170">O comportamento específico deste último depende da utilização do simulador, mas normalmente escreve uma mensagem para a consola anfitriã quando é chamada durante um programa Q#.</span><span class="sxs-lookup"><span data-stu-id="a5890-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="a5890-171">As cordas em Q# são literais ou cordas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="a5890-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="a5890-172">As letras de corda são semelhantes às simples cordas literais na maioria das línguas: uma sequência de caracteres Unicode incluídos em citações duplas, `"` .</span><span class="sxs-lookup"><span data-stu-id="a5890-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="a5890-173">Dentro de uma corda, o personagem de barra traseira `\` pode ser usado para escapar de um personagem de dupla citação, e para inserir uma nova linha como , um retorno de `\n` carruagem como , e uma guia `\r` como `\t` .</span><span class="sxs-lookup"><span data-stu-id="a5890-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="a5890-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a5890-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="a5890-175">Cordas interpoladas</span><span class="sxs-lookup"><span data-stu-id="a5890-175">Interpolated strings</span></span>

<span data-ttu-id="a5890-176">A sintaxe Q# para interpolações de cordas é um subconjunto da sintaxe C#, mas resumimos aqui os pontos-chave que dizem respeito a Q#.</span><span class="sxs-lookup"><span data-stu-id="a5890-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="a5890-177">As principais distinções são discutidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a5890-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="a5890-178">Para identificar uma corda literal como uma corda interpolada, prepare-a com o `$` símbolo.</span><span class="sxs-lookup"><span data-stu-id="a5890-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="a5890-179">Não se pode ter nenhum espaço em branco entre o `$` e o que começa uma corda `"` literal.</span><span class="sxs-lookup"><span data-stu-id="a5890-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="a5890-180">O seguinte é um exemplo básico usando a [`Message`](xref:microsoft.quantum.intrinsic.message) função para escrever o resultado de uma medição para a consola, ao lado de outras expressões Q#.</span><span class="sxs-lookup"><span data-stu-id="a5890-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="a5890-181">Qualquer expressão Q# válida pode aparecer numa corda interpolada.</span><span class="sxs-lookup"><span data-stu-id="a5890-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="a5890-182">Mais detalhes sobre a sintaxe C# podem ser encontrados em [*Cordas Interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="a5890-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="a5890-183">A distinção mais notável é que Q# não suporta cordas interpoladas verbatim (multi-line).</span><span class="sxs-lookup"><span data-stu-id="a5890-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="a5890-184">Expressões dentro de uma corda interpolada seguem a sintaxe Q#, não a sintaxe C#.</span><span class="sxs-lookup"><span data-stu-id="a5890-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="a5890-185">Expressões de alcance</span><span class="sxs-lookup"><span data-stu-id="a5890-185">Range Expressions</span></span>

<span data-ttu-id="a5890-186">Tendo em conta as três `Int` expressões `start` , e , é uma expressão de alcance cujo primeiro elemento é , o segundo `step` elemento é , o terceiro elemento é , `stop` `start .. step .. stop` `start` `start+step` `start+step+step` etc., até `stop` ser passado.</span><span class="sxs-lookup"><span data-stu-id="a5890-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="a5890-187">Um intervalo pode estar vazio se, por exemplo, `step` for positivo e `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="a5890-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="a5890-188">O último elemento da gama será `stop` se a diferença entre e é um `start` `stop` múltiplo integral `step` de; ou seja, a gama é inclusiva em ambas as extremidades.</span><span class="sxs-lookup"><span data-stu-id="a5890-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="a5890-189">Tendo em conta `Int` duas expressões `start` `stop` e, `start .. stop` é uma expressão de alcance que é igual a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="a5890-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="a5890-190">Note que o implícito `step` é +1 mesmo que `stop` seja `start` inferior; em tal caso, o intervalo está vazio.</span><span class="sxs-lookup"><span data-stu-id="a5890-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="a5890-191">Algumas gamas de exemplos são:</span><span class="sxs-lookup"><span data-stu-id="a5890-191">Some example ranges are:</span></span>

- <span data-ttu-id="a5890-192">`1..3`é o alcance 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="a5890-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="a5890-193">`2..2..5`é o alcance 2, 4.</span><span class="sxs-lookup"><span data-stu-id="a5890-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="a5890-194">`2..2..6`é o alcance 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="a5890-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="a5890-195">`6..-2..2`é o alcance 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="a5890-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="a5890-196">`2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="a5890-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="a5890-197">`2..6..7`é o alcance 2.</span><span class="sxs-lookup"><span data-stu-id="a5890-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="a5890-198">`2..2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="a5890-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="a5890-199">`1..-1..2`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="a5890-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="a5890-200">Expressões qubit</span><span class="sxs-lookup"><span data-stu-id="a5890-200">Qubit Expressions</span></span>

<span data-ttu-id="a5890-201">As `Qubit` únicas expressões são símbolos que estão ligados a `Qubit` valores ou elementos de `Qubit` matrizes.</span><span class="sxs-lookup"><span data-stu-id="a5890-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="a5890-202">Não há `Qubit` literais.</span><span class="sxs-lookup"><span data-stu-id="a5890-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="a5890-203">Expressões Pauli</span><span class="sxs-lookup"><span data-stu-id="a5890-203">Pauli Expressions</span></span>

<span data-ttu-id="a5890-204">Os quatro `Pauli` valores são `PauliI` `PauliX` `PauliY` `PauliZ` `Pauli` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="a5890-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="a5890-205">Para além disso, as `Pauli` únicas expressões são símbolos que estão ligados a `Pauli` valores ou elementos de `Pauli` matrizes.</span><span class="sxs-lookup"><span data-stu-id="a5890-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="a5890-206">Expressões de resultados</span><span class="sxs-lookup"><span data-stu-id="a5890-206">Result Expressions</span></span>

<span data-ttu-id="a5890-207">Os dois `Result` `One` valores, `Zero` e, são `Result` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="a5890-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="a5890-208">Para além disso, as `Result` únicas expressões são símbolos que estão ligados a `Result` valores ou elementos de `Result` matrizes.</span><span class="sxs-lookup"><span data-stu-id="a5890-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="a5890-209">Em particular, note que não é o mesmo que `One` o inteiro , e não há conversão direta entre `1` eles.</span><span class="sxs-lookup"><span data-stu-id="a5890-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="a5890-210">O mesmo se aplica `Zero` `0` e. .</span><span class="sxs-lookup"><span data-stu-id="a5890-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="a5890-211">Expressões tuple</span><span class="sxs-lookup"><span data-stu-id="a5890-211">Tuple Expressions</span></span>

<span data-ttu-id="a5890-212">Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="a5890-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="a5890-213">Por exemplo, `(1, One)` é uma `(Int, Result)` expressão.</span><span class="sxs-lookup"><span data-stu-id="a5890-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="a5890-214">Além das literais, as únicas expressões de tuple são símbolos que são obrigados a tuple valores, elementos de matrizes de tuple, e invocações callable que devolvem tuples.</span><span class="sxs-lookup"><span data-stu-id="a5890-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="a5890-215">Expressões de tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="a5890-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="a5890-216">Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.</span><span class="sxs-lookup"><span data-stu-id="a5890-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="a5890-217">Por exemplo, se `IntPair` for um tipo definido pelo utilizador baseado em , `(Int, Int)` então seria um literal válido desse `IntPair(2, 3)` tipo.</span><span class="sxs-lookup"><span data-stu-id="a5890-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="a5890-218">Além das literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos de matrizes desse tipo, e invocações pôveis que devolvem esse tipo.</span><span class="sxs-lookup"><span data-stu-id="a5890-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="a5890-219">Desembrulhar expressões</span><span class="sxs-lookup"><span data-stu-id="a5890-219">Unwrap Expressions</span></span>

<span data-ttu-id="a5890-220">Em Q#, o operador de desembrulhar é um ponto de exclamação em fuga `!` .</span><span class="sxs-lookup"><span data-stu-id="a5890-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="a5890-221">Por exemplo, se `IntPair` for um tipo definido pelo utilizador com tipo `(Int, Int)` subjacente, e fosse uma `s` variável com `IntPair(2, 3)` valor, então `s!` seria `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="a5890-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="a5890-222">Para os tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador, o operador de desembrulhá-lo pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s` .</span><span class="sxs-lookup"><span data-stu-id="a5890-222">For user-defined types defined in terms of other user-defined types, the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="a5890-223">Assim, se `WrappedPair` for um tipo definido pelo utilizador com tipo `IntPair` subjacente, e é uma `t` variável com `WrappedPair(IntPair(1,2))` valor, então `t!!` seria `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="a5890-223">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="a5890-224">O `!` operador tem uma precedência mais elevada do que todos os outros operadores que não para a `[]` indexação e corte de matrizes.</span><span class="sxs-lookup"><span data-stu-id="a5890-224">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="a5890-225">`!`e `[]` ligar posicionalmente; ou seja, `a[i]![3]` deve ser lido como : pegue no `((a[i])!)[3]` `i` 'th elemento de `a` , desembrulhá-lo, e, em seguida, obter o terceiro elemento do valor desembrulhado (que deve ser uma matriz).</span><span class="sxs-lookup"><span data-stu-id="a5890-225">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="a5890-226">A precedência do `!` operador tem um impacto que pode não ser óbvio.</span><span class="sxs-lookup"><span data-stu-id="a5890-226">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="a5890-227">Se uma função ou operação devolver um valor que seja desembrulhado, a função ou chamada de funcionamento deve ser fechada em parênteses para que o argumento se ligue à chamada e não ao desembrulho.</span><span class="sxs-lookup"><span data-stu-id="a5890-227">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="a5890-228">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a5890-228">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="a5890-229">Expressões de matriz</span><span class="sxs-lookup"><span data-stu-id="a5890-229">Array Expressions</span></span>

<span data-ttu-id="a5890-230">Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas `[` e `]` .</span><span class="sxs-lookup"><span data-stu-id="a5890-230">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="a5890-231">Todos os elementos devem ser compatíveis com o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="a5890-231">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="a5890-232">Tendo em conta duas matrizes do mesmo tipo, o operador binário `+` pode ser utilizado para formar uma nova matriz que é a concatenação das duas matrizes.</span><span class="sxs-lookup"><span data-stu-id="a5890-232">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="a5890-233">Por exemplo, `[1,2,3] + [4,5,6]` é `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="a5890-233">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="a5890-234">Criação de Matrizes</span><span class="sxs-lookup"><span data-stu-id="a5890-234">Array Creation</span></span>

<span data-ttu-id="a5890-235">Dado um tipo e uma `Int` expressão, o `new` operador pode ser utilizado para alocar uma nova matriz do tamanho dado.</span><span class="sxs-lookup"><span data-stu-id="a5890-235">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="a5890-236">Por exemplo, `new Int[i + 1]` atribuiria uma nova `Int` matriz com `i + 1` elementos.</span><span class="sxs-lookup"><span data-stu-id="a5890-236">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="a5890-237">Não são permitidos literais de matrizes `[]` vazias.</span><span class="sxs-lookup"><span data-stu-id="a5890-237">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="a5890-238">Em vez disso, a utilização `new ★[0]` , onde é reservado para um tipo `★` adequado, permite criar a matriz de comprimento zero desejada.</span><span class="sxs-lookup"><span data-stu-id="a5890-238">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="a5890-239">Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.</span><span class="sxs-lookup"><span data-stu-id="a5890-239">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="a5890-240">Na maioria dos casos, esta é uma variação de zero.</span><span class="sxs-lookup"><span data-stu-id="a5890-240">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="a5890-241">Para qubits e callables, que são referências a entidades, não existe um valor padrão razoável.</span><span class="sxs-lookup"><span data-stu-id="a5890-241">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="a5890-242">Assim, para estes tipos, o padrão é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a5890-242">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="a5890-243">Isto é semelhante a uma referência nula em línguas como C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="a5890-243">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="a5890-244">Os conjuntos que contenham qubits ou calcáveis devem ser corretamente inicializados com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança.</span><span class="sxs-lookup"><span data-stu-id="a5890-244">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="a5890-245">As rotinas de inicialização adequadas podem ser encontradas em <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="a5890-245">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="a5890-246">Os valores predefinidos para cada tipo são:</span><span class="sxs-lookup"><span data-stu-id="a5890-246">The default values for each type are:</span></span>

<span data-ttu-id="a5890-247">Tipo</span><span class="sxs-lookup"><span data-stu-id="a5890-247">Type</span></span> | <span data-ttu-id="a5890-248">Predefinição</span><span class="sxs-lookup"><span data-stu-id="a5890-248">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="a5890-249">_qubit inválido_</span><span class="sxs-lookup"><span data-stu-id="a5890-249">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="a5890-250">A gama vazia,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="a5890-250">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="a5890-251">_inválido callable_</span><span class="sxs-lookup"><span data-stu-id="a5890-251">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="a5890-252">Os tipos de tuple são elemento-por-elemento inicializados.</span><span class="sxs-lookup"><span data-stu-id="a5890-252">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="a5890-253">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="a5890-253">Array Elements</span></span>

<span data-ttu-id="a5890-254">Dada a expressão de matriz e uma `Int` expressão, uma nova expressão pode ser formada usando o operador de `[` elementos de matriz e `]` matriz.</span><span class="sxs-lookup"><span data-stu-id="a5890-254">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="a5890-255">A nova expressão será do mesmo tipo que o tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="a5890-255">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="a5890-256">Por exemplo, se `a` está ligado a uma matriz de `Double` s, então `a[4]` é uma `Double` expressão.</span><span class="sxs-lookup"><span data-stu-id="a5890-256">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="a5890-257">Se a expressão da matriz não for um identificador simples, deve ser fechada em parênteses para selecionar um elemento.</span><span class="sxs-lookup"><span data-stu-id="a5890-257">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="a5890-258">Por exemplo, se `a` e `b` forem ambos conjuntos de `Int` s, um elemento da concatenação seria expresso como:</span><span class="sxs-lookup"><span data-stu-id="a5890-258">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="a5890-259">Todos os arrays em Q# são baseados em zero.</span><span class="sxs-lookup"><span data-stu-id="a5890-259">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="a5890-260">Ou seja, o primeiro elemento de uma matriz `a` é `a[0]` sempre.</span><span class="sxs-lookup"><span data-stu-id="a5890-260">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="a5890-261">Fatias de Matriz</span><span class="sxs-lookup"><span data-stu-id="a5890-261">Array Slices</span></span>

<span data-ttu-id="a5890-262">Dada a expressão de matriz e uma `Range` expressão, uma nova expressão pode ser formada usando o operador de `[` fatias de `]` matriz e matriz.</span><span class="sxs-lookup"><span data-stu-id="a5890-262">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="a5890-263">A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range` , na ordem definida pelo `Range` .</span><span class="sxs-lookup"><span data-stu-id="a5890-263">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="a5890-264">Por exemplo, se `a` estiver ligado a um conjunto de `Double` s, então `a[3..-1..0]` é uma expressão que contém os `Double[]` primeiros quatro elementos de `a` mas na ordem inversa como aparecem em `a` .</span><span class="sxs-lookup"><span data-stu-id="a5890-264">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="a5890-265">Se a `Range` fatia estiver vazia, a fatia de matriz resultante terá um comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="a5890-265">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="a5890-266">Tal como acontece com os elementos de matriz de referência, se a expressão da matriz não for um simples identificador, deve ser fechada parênteses para cortar.</span><span class="sxs-lookup"><span data-stu-id="a5890-266">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="a5890-267">Se `a` e forem ambos `b` conjuntos de `Int` s, uma fatia da concatenação seria expressa como:</span><span class="sxs-lookup"><span data-stu-id="a5890-267">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="a5890-268">Valores inferidos de início/fim</span><span class="sxs-lookup"><span data-stu-id="a5890-268">Inferred start/end values</span></span>

<span data-ttu-id="a5890-269">Começando com o nosso lançamento 0.8, apoiamos expressões contextuais para corte de alcance.</span><span class="sxs-lookup"><span data-stu-id="a5890-269">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="a5890-270">Em especial, os valores de arranque e de fim de gama podem ser omitidos no contexto de uma expressão de corte de gama.</span><span class="sxs-lookup"><span data-stu-id="a5890-270">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="a5890-271">Nesse caso, o compilador aplicará as seguintes regras para inferir os delimiters previstos para o intervalo.</span><span class="sxs-lookup"><span data-stu-id="a5890-271">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="a5890-272">Por exemplo, se o valor inicial da gama for omitido, então o valor inicial inferido</span><span class="sxs-lookup"><span data-stu-id="a5890-272">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="a5890-273">é zero se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="a5890-273">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="a5890-274">é o comprimento da matriz fatiada menos um se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="a5890-274">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="a5890-275">Se o valor final da gama for omitido, então o valor final inferido</span><span class="sxs-lookup"><span data-stu-id="a5890-275">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="a5890-276">é o comprimento da matriz fatiada menos um se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="a5890-276">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="a5890-277">é zero se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="a5890-277">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="a5890-278">Expressões de cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="a5890-278">Copy-and-Update Expressions</span></span>

<span data-ttu-id="a5890-279">Uma vez que todos os tipos Q# são tipos de valor — com os qubits a assumirem um papel um pouco especial — formalmente é criada uma "cópia" quando um valor está ligado a um símbolo, ou quando um símbolo é recuperado.</span><span class="sxs-lookup"><span data-stu-id="a5890-279">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="a5890-280">Ou seja, o comportamento de Q# é o mesmo que se uma cópia fosse criada numa missão.</span><span class="sxs-lookup"><span data-stu-id="a5890-280">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="a5890-281">Naturalmente, na prática, apenas as peças relevantes são recriadas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="a5890-281">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="a5890-282">Isto inclui também matrizes.</span><span class="sxs-lookup"><span data-stu-id="a5890-282">This in particular also includes arrays.</span></span>
<span data-ttu-id="a5890-283">Em particular, não é possível atualizar os itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="a5890-283">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="a5890-284">Modificar uma matriz existente requer uma alavancagem de um mecanismo *de cópia e atualização.*</span><span class="sxs-lookup"><span data-stu-id="a5890-284">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="a5890-285">Novas matrizes podem ser criadas a partir das existentes através de expressões *de cópia e atualização.*</span><span class="sxs-lookup"><span data-stu-id="a5890-285">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="a5890-286">Uma expressão de cópia e atualização é uma expressão do `expression1 w/ expression2 <- expression3` formulário, onde `expression1` tem de ser do tipo para algum tipo `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="a5890-286">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="a5890-287">O segundo `expression2` define os índices dos elementos(s) para modificar em comparação com a matriz `expression1` e tem de ser de tipo ou de tipo `Int` `Range` .</span><span class="sxs-lookup"><span data-stu-id="a5890-287">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="a5890-288">Se `expression2` for do `Int` tipo, tem de ser do `expression3` `T` tipo.</span><span class="sxs-lookup"><span data-stu-id="a5890-288">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="a5890-289">Se `expression2` for do `Range` tipo, tem de ser do `expression3` `T[]` tipo.</span><span class="sxs-lookup"><span data-stu-id="a5890-289">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="a5890-290">Uma expressão de cópia e atualização `arr w/ idx <- value` constrói uma nova matriz com todos os elementos definidos para o elemento correspondente em , exceto os `arr` elementos em , que são `idx` definidos para o(s) em `value` .</span><span class="sxs-lookup"><span data-stu-id="a5890-290">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="a5890-291">Por exemplo, se `arr` contiver uma `[0,1,2,3]` matriz, então</span><span class="sxs-lookup"><span data-stu-id="a5890-291">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="a5890-292">`arr w/ 0 <- 10`é a matriz `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="a5890-292">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="a5890-293">`arr w/ 2 <- 10`é a matriz `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="a5890-293">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="a5890-294">`arr w/ 0..2..3 <- [10,12]`é a matriz `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="a5890-294">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="a5890-295">Expressões de cópia e atualização para itens nomeados</span><span class="sxs-lookup"><span data-stu-id="a5890-295">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="a5890-296">Expressões semelhantes existem para itens nomeados em tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="a5890-296">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="a5890-297">Considere, por exemplo, o tipo</span><span class="sxs-lookup"><span data-stu-id="a5890-297">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="a5890-298">Se `c` contiver o valor do `Complex(1., -1.)` tipo, então `c w/ Re <- 0.` é uma expressão do tipo que avalia `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="a5890-298">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="a5890-299">Matrizes irregulares</span><span class="sxs-lookup"><span data-stu-id="a5890-299">Jagged Arrays</span></span>

<span data-ttu-id="a5890-300">Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes.</span><span class="sxs-lookup"><span data-stu-id="a5890-300">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="a5890-301">Os elementos de uma matriz irregular podem ser de diferentes tamanhos.</span><span class="sxs-lookup"><span data-stu-id="a5890-301">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="a5890-302">O exemplo a seguir mostra como declarar e inicializar uma matriz irregular que representa uma tabela de multiplicação.</span><span class="sxs-lookup"><span data-stu-id="a5890-302">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="a5890-303">Matrizes de callables</span><span class="sxs-lookup"><span data-stu-id="a5890-303">Arrays of callables</span></span> 

<span data-ttu-id="a5890-304">Note que mais detalhes sobre tipos de chamadas podem ser encontrados abaixo, bem como na página seguinte, [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="a5890-304">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="a5890-305">Se o tipo de elemento comum for um tipo de funcionamento ou função, todos os elementos devem ter os mesmos tipos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="a5890-305">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="a5890-306">O tipo de elemento da matriz irá suportar quaisquer funtores que sejam suportados por todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="a5890-306">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="a5890-307">Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="a5890-307">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="a5890-308">`[Op1, Op2]`é uma série de `(Qubit[] => Unit)` operações.</span><span class="sxs-lookup"><span data-stu-id="a5890-308">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="a5890-309">`[Op1, Op3]`é uma série de `(Qubit[] => Unit is Adj)` operações.</span><span class="sxs-lookup"><span data-stu-id="a5890-309">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="a5890-310">`[Op2, Op3]`é uma série de `(Qubit[] => Unit is Ctl)` operações.</span><span class="sxs-lookup"><span data-stu-id="a5890-310">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="a5890-311">No entanto, embora `(Qubit[] => Unit is Adj)` as `(Qubit[] => Unit is Ctl)` operações tenham o tipo de base comum `(Qubit[] => Unit)` de, note-se que as matrizes destes operadores não partilham um tipo de base comum. *of*</span><span class="sxs-lookup"><span data-stu-id="a5890-311">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="a5890-312">Por exemplo, `[[Op1], [Op2]]` atualmente levantaria um erro porque está a tentar criar uma matriz dos tipos de matrizes incompatíveis `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="a5890-312">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="a5890-313">Expressões Condicionais</span><span class="sxs-lookup"><span data-stu-id="a5890-313">Conditional Expressions</span></span>

<span data-ttu-id="a5890-314">Tendo em conta duas outras expressões do mesmo tipo e uma expressão booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação `?` e a barra vertical `|` .</span><span class="sxs-lookup"><span data-stu-id="a5890-314">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="a5890-315">Por exemplo, `a==b ? c | d` . .</span><span class="sxs-lookup"><span data-stu-id="a5890-315">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="a5890-316">Neste exemplo, o valor da expressão condicional será `c` se for verdade e se for `a==b` `d` falso.</span><span class="sxs-lookup"><span data-stu-id="a5890-316">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="a5890-317">Expressões condicionais com callables</span><span class="sxs-lookup"><span data-stu-id="a5890-317">Conditional expressions with callables</span></span>

<span data-ttu-id="a5890-318">As duas expressões podem avaliar operações que tenham as mesmas entradas e saídas, mas suportam diferentes functors.</span><span class="sxs-lookup"><span data-stu-id="a5890-318">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="a5890-319">Neste caso, o tipo de expressão condicional é uma operação com as entradas e saídas que suportam quaisquer funtores apoiados por ambas as expressões.</span><span class="sxs-lookup"><span data-stu-id="a5890-319">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="a5890-320">Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="a5890-320">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="a5890-321">`flag ? Op1 | Op2`é uma `(Qubit[] => Unit)` operação.</span><span class="sxs-lookup"><span data-stu-id="a5890-321">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="a5890-322">`flag ? Op1 | Op3`é uma `(Qubit[] => Unit is Adj)` operação.</span><span class="sxs-lookup"><span data-stu-id="a5890-322">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="a5890-323">`flag ? Op2 | Op3`é uma `(Qubit[] => Unit is Ctl)` operação.</span><span class="sxs-lookup"><span data-stu-id="a5890-323">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="a5890-324">Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de funcionamento, essa chamada só será efetuada se esse resultado for o valor da chamada.</span><span class="sxs-lookup"><span data-stu-id="a5890-324">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="a5890-325">Por exemplo, no caso `a==b ? C(qs) | D(qs)` , se `a==b` for verdade, a `C` operação será invocada, e se for falsa, só `D` será invocada.</span><span class="sxs-lookup"><span data-stu-id="a5890-325">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="a5890-326">Isto é semelhante ao curto-circuito em outras línguas.</span><span class="sxs-lookup"><span data-stu-id="a5890-326">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="a5890-327">Expressões calláveis</span><span class="sxs-lookup"><span data-stu-id="a5890-327">Callable Expressions</span></span>

<span data-ttu-id="a5890-328">Um literal chamado é o nome de uma operação ou função definida no âmbito de compilação.</span><span class="sxs-lookup"><span data-stu-id="a5890-328">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="a5890-329">Por exemplo, `X` é uma operação literal que se refere à operação padrão da `X` biblioteca, e é uma `Message` função literal que se refere à função de biblioteca `Message` padrão.</span><span class="sxs-lookup"><span data-stu-id="a5890-329">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="a5890-330">Se uma operação suporta o `Adjoint` functor, então `Adjoint op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="a5890-330">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="a5890-331">Da mesma forma, se a operação suporta o `Controlled` functor, então `Controlled op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="a5890-331">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="a5890-332">Os tipos destas expressões são especificados nas [especializações da operação Call](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="a5890-332">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="a5890-333">Os functores `Adjoint` (e `Controlled` ) ligam-se mais estreitamente do que todos os outros operadores, com exceção do operador de desembrulhar `!` e da indexação da matriz com []».</span><span class="sxs-lookup"><span data-stu-id="a5890-333">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="a5890-334">Assim, todos são legais, assumindo que as operações suportam os funtores utilizados:</span><span class="sxs-lookup"><span data-stu-id="a5890-334">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="a5890-335">Expressões de caloisos por tipo parametrizadas</span><span class="sxs-lookup"><span data-stu-id="a5890-335">Type-parameterized callable expressions</span></span>

<span data-ttu-id="a5890-336">Um literal chamado pode ser usado como um valor, por exemplo, para atribuir a uma variável ou para passar para outra chamada.</span><span class="sxs-lookup"><span data-stu-id="a5890-336">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="a5890-337">Neste caso, se a chamada tiver [parâmetros de tipo,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)devem ser fornecidos como parte do valor de chamada.</span><span class="sxs-lookup"><span data-stu-id="a5890-337">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="a5890-338">Um valor calável não pode ter parâmetros de tipo não especificados.</span><span class="sxs-lookup"><span data-stu-id="a5890-338">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="a5890-339">Por exemplo, se `Fun` for uma função com `'T1->Unit` assinatura:</span><span class="sxs-lookup"><span data-stu-id="a5890-339">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="a5890-340">Expressões de invocação callable</span><span class="sxs-lookup"><span data-stu-id="a5890-340">Callable Invocation Expressions</span></span>

<span data-ttu-id="a5890-341">Dada uma expressão callable (operação ou função) e uma expressão tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada por anexar a expressão de tuple à expressão callable.</span><span class="sxs-lookup"><span data-stu-id="a5890-341">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="a5890-342">O tipo de expressão de invocação é o tipo de saída da assinatura do callable.</span><span class="sxs-lookup"><span data-stu-id="a5890-342">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="a5890-343">Por exemplo, se `Op` for uma operação com `((Int, Qubit) => Double)` assinatura, é uma expressão do tipo `Op(3, qubit1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="a5890-343">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="a5890-344">Da mesma forma, se `Sin` for uma função com `(Double -> Double)` assinatura, é uma expressão do tipo `Sin(0.1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="a5890-344">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="a5890-345">Finalmente, se `Builder` é uma função com `(Int -> (Int -> Int))` assinatura, então `Builder(3)` é uma função de Into to Int.</span><span class="sxs-lookup"><span data-stu-id="a5890-345">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="a5890-346">Invocar o resultado de uma expressão de valor callable requer um par extra de parênteses em torno da expressão callable.</span><span class="sxs-lookup"><span data-stu-id="a5890-346">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="a5890-347">Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:</span><span class="sxs-lookup"><span data-stu-id="a5890-347">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="a5890-348">Ao invocar uma chamada [tipo-parametrizada,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) os parâmetros do tipo real podem ser especificados dentro dos suportes angulares `<` e após a expressão `>` callable.</span><span class="sxs-lookup"><span data-stu-id="a5890-348">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="a5890-349">Isto é geralmente desnecessário, uma vez que o compilador Q# infere os tipos reais.</span><span class="sxs-lookup"><span data-stu-id="a5890-349">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="a5890-350">No entanto, *é* necessário para [a aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se um argumento porontose de tipo não for especificado.</span><span class="sxs-lookup"><span data-stu-id="a5890-350">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="a5890-351">Também é por vezes útil ao passar operações com diferentes suportes de functor para um callable.</span><span class="sxs-lookup"><span data-stu-id="a5890-351">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="a5890-352">Por exemplo, se `Func` tiver assinatura , e ter assinatura , e tiver assinatura , para invocar `('T1, 'T2, 'T1) -> 'T2` como primeiro `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` `Op1` argumento, como o `Op2` segundo, e como o `Op3` terceiro:</span><span class="sxs-lookup"><span data-stu-id="a5890-352">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="a5890-353">A especificação do tipo é necessária porque `Op3` e `Op1` tem diferentes tipos, de modo que o compilador tratará isto como ambíguo sem a especificação.</span><span class="sxs-lookup"><span data-stu-id="a5890-353">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="a5890-354">Precedência do operador</span><span class="sxs-lookup"><span data-stu-id="a5890-354">Operator Precedence</span></span>

<span data-ttu-id="a5890-355">Todos os operadores binários são associados à direita, `^` exceto.</span><span class="sxs-lookup"><span data-stu-id="a5890-355">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="a5890-356">Os suportes `[` `]` e, para cortar e indexar a matriz, ligam-se perante qualquer operador.</span><span class="sxs-lookup"><span data-stu-id="a5890-356">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="a5890-357">Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.</span><span class="sxs-lookup"><span data-stu-id="a5890-357">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="a5890-358">Os parênteses para a invocação de funcionamento e função também se ligam perante qualquer operador, mas após a indexação de matrizes e funtores.</span><span class="sxs-lookup"><span data-stu-id="a5890-358">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="a5890-359">Operadores por ordem de precedência, da mais alta para a mais baixa:</span><span class="sxs-lookup"><span data-stu-id="a5890-359">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="a5890-360">Operador</span><span class="sxs-lookup"><span data-stu-id="a5890-360">Operator</span></span> | <span data-ttu-id="a5890-361">Arity</span><span class="sxs-lookup"><span data-stu-id="a5890-361">Arity</span></span> | <span data-ttu-id="a5890-362">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5890-362">Description</span></span> | <span data-ttu-id="a5890-363">Tipos operand</span><span class="sxs-lookup"><span data-stu-id="a5890-363">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="a5890-364">trailing`!`</span><span class="sxs-lookup"><span data-stu-id="a5890-364">trailing `!`</span></span> | <span data-ttu-id="a5890-365">Unária</span><span class="sxs-lookup"><span data-stu-id="a5890-365">Unary</span></span> | <span data-ttu-id="a5890-366">Desembrulhar</span><span class="sxs-lookup"><span data-stu-id="a5890-366">Unwrap</span></span> | <span data-ttu-id="a5890-367">Qualquer tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="a5890-367">Any user-defined type</span></span>
 <span data-ttu-id="a5890-368">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="a5890-368">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="a5890-369">Unária</span><span class="sxs-lookup"><span data-stu-id="a5890-369">Unary</span></span> | <span data-ttu-id="a5890-370">Numérico negativo, complemento bitwise, negação lógica</span><span class="sxs-lookup"><span data-stu-id="a5890-370">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="a5890-371">`Int`, `BigInt` ou `Double` `-` para, ou para `Int` `BigInt` `~~~` , `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="a5890-371">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="a5890-372">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-372">Binary</span></span> | <span data-ttu-id="a5890-373">Poder inteiro</span><span class="sxs-lookup"><span data-stu-id="a5890-373">Integer power</span></span> | <span data-ttu-id="a5890-374">`Int`ou `BigInt` para a base, para o `Int` expoente</span><span class="sxs-lookup"><span data-stu-id="a5890-374">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="a5890-375">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="a5890-375">`/`, `*`, `%`</span></span> | <span data-ttu-id="a5890-376">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-376">Binary</span></span> | <span data-ttu-id="a5890-377">Divisão, multiplicação, módulo inteiro</span><span class="sxs-lookup"><span data-stu-id="a5890-377">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="a5890-378">`Int`, `BigInt` ou `Double` para `/` `*` e, ou `Int` `BigInt` para`%`</span><span class="sxs-lookup"><span data-stu-id="a5890-378">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="a5890-379">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="a5890-379">`+`, `-`</span></span> | <span data-ttu-id="a5890-380">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-380">Binary</span></span> | <span data-ttu-id="a5890-381">Adição ou cadeia e concatenação de matriz, subtração</span><span class="sxs-lookup"><span data-stu-id="a5890-381">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="a5890-382">`Int`, `BigInt` ou `Double` , adicionalmente ou qualquer tipo de matriz `String` para`+`</span><span class="sxs-lookup"><span data-stu-id="a5890-382">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="a5890-383">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="a5890-383">`<<<`, `>>>`</span></span> | <span data-ttu-id="a5890-384">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-384">Binary</span></span> | <span data-ttu-id="a5890-385">Turno da esquerda, turno da direita</span><span class="sxs-lookup"><span data-stu-id="a5890-385">Left shift, right shift</span></span> | <span data-ttu-id="a5890-386">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="a5890-386">`Int` or `BigInt`</span></span>
 <span data-ttu-id="a5890-387">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="a5890-387">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="a5890-388">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-388">Binary</span></span> | <span data-ttu-id="a5890-389">Comparações menos do que, menos ou iguais, maiores do que, maiores do que iguais</span><span class="sxs-lookup"><span data-stu-id="a5890-389">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="a5890-390">`Int`, `BigInt` ou`Double`</span><span class="sxs-lookup"><span data-stu-id="a5890-390">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="a5890-391">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="a5890-391">`==`, `!=`</span></span> | <span data-ttu-id="a5890-392">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-392">Binary</span></span> | <span data-ttu-id="a5890-393">comparações iguais e não iguais</span><span class="sxs-lookup"><span data-stu-id="a5890-393">equal, not-equal comparisons</span></span> | <span data-ttu-id="a5890-394">qualquer tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="a5890-394">any primitive type</span></span>
 `&&&` | <span data-ttu-id="a5890-395">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-395">Binary</span></span> | <span data-ttu-id="a5890-396">Bitwise E</span><span class="sxs-lookup"><span data-stu-id="a5890-396">Bitwise AND</span></span> | <span data-ttu-id="a5890-397">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="a5890-397">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="a5890-398">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-398">Binary</span></span> | <span data-ttu-id="a5890-399">Bitwise XOR</span><span class="sxs-lookup"><span data-stu-id="a5890-399">Bitwise XOR</span></span> | <span data-ttu-id="a5890-400">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="a5890-400">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="a5890-401">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-401">Binary</span></span> | <span data-ttu-id="a5890-402">Bitwise OR</span><span class="sxs-lookup"><span data-stu-id="a5890-402">Bitwise OR</span></span> | <span data-ttu-id="a5890-403">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="a5890-403">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="a5890-404">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-404">Binary</span></span> | <span data-ttu-id="a5890-405">AND lógico</span><span class="sxs-lookup"><span data-stu-id="a5890-405">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="a5890-406">Binário</span><span class="sxs-lookup"><span data-stu-id="a5890-406">Binary</span></span> | <span data-ttu-id="a5890-407">OR lógico</span><span class="sxs-lookup"><span data-stu-id="a5890-407">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="a5890-408">Binário/Ternário</span><span class="sxs-lookup"><span data-stu-id="a5890-408">Binary/Ternary</span></span> | <span data-ttu-id="a5890-409">Operador de gama</span><span class="sxs-lookup"><span data-stu-id="a5890-409">Range operator</span></span> | `Int`
 <span data-ttu-id="a5890-410">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="a5890-410">`?` `|`</span></span> | <span data-ttu-id="a5890-411">Ternário</span><span class="sxs-lookup"><span data-stu-id="a5890-411">Ternary</span></span> | <span data-ttu-id="a5890-412">Condicional</span><span class="sxs-lookup"><span data-stu-id="a5890-412">Conditional</span></span> | <span data-ttu-id="a5890-413">`Bool`para o lado esquerdo</span><span class="sxs-lookup"><span data-stu-id="a5890-413">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="a5890-414">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="a5890-414">`w/` `<-`</span></span> | <span data-ttu-id="a5890-415">Ternário</span><span class="sxs-lookup"><span data-stu-id="a5890-415">Ternary</span></span> | <span data-ttu-id="a5890-416">Cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="a5890-416">Copy-and-update</span></span> | <span data-ttu-id="a5890-417">ver [expressões de cópia e atualização](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="a5890-417">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5890-418">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="a5890-418">Next steps</span></span>

<span data-ttu-id="a5890-419">Agora que pode trabalhar com expressões em Q#, pode dirigir-se a [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions) para aprender a definir e chamar operações e funções.</span><span class="sxs-lookup"><span data-stu-id="a5890-419">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
