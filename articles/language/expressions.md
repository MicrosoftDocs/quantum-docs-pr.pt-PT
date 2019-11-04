---
title: Expressões | Microsoft Docs
description: Expressões
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 09d493df4e1178fee1f7a5946cfda2f411111006
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185210"
---
# <a name="expressions"></a><span data-ttu-id="f47b3-103">Expressões</span><span class="sxs-lookup"><span data-stu-id="f47b3-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="f47b3-104">Agrupamento</span><span class="sxs-lookup"><span data-stu-id="f47b3-104">Grouping</span></span>

<span data-ttu-id="f47b3-105">Dada qualquer expressão, a mesma expressão entre parênteses é uma expressão do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="f47b3-106">Por exemplo, `(7)` é uma expressão de `Int`, `([1,2,3])` é uma expressão do tipo matriz de `Int`s e `((1,2))` é uma expressão com o tipo `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="f47b3-107">A equivalência entre valores simples e tuplas de elemento único descritos no [modelo de tipo](xref:microsoft.quantum.language.type-model#tuple-types) remove a ambiguidade entre `(6)` como um grupo e `(6)` como uma tupla de elemento único.</span><span class="sxs-lookup"><span data-stu-id="f47b3-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="f47b3-108">Symbol</span><span class="sxs-lookup"><span data-stu-id="f47b3-108">Symbols</span></span>

<span data-ttu-id="f47b3-109">O nome de um símbolo associado ou atribuído a um valor do tipo `'T` é uma expressão do tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="f47b3-110">Por exemplo, se o símbolo `count` estiver associado ao valor inteiro `5`, `count` será uma expressão de número inteiro.</span><span class="sxs-lookup"><span data-stu-id="f47b3-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="f47b3-111">Expressões numéricas</span><span class="sxs-lookup"><span data-stu-id="f47b3-111">Numeric Expressions</span></span>

<span data-ttu-id="f47b3-112">Expressões numéricas são expressões do tipo `Int`, `BigInt`ou `Double`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="f47b3-113">Ou seja, eles são números inteiros ou de ponto flutuante.</span><span class="sxs-lookup"><span data-stu-id="f47b3-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="f47b3-114">os literais `Int` em Q # são idênticos aos literais C#inteiros no, exceto pelo fato de que nenhum "l" ou "l" à direita é necessário (ou permitido).</span><span class="sxs-lookup"><span data-stu-id="f47b3-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="f47b3-115">Os inteiros hexadecimais e binários têm suporte com um prefixo "0x" e "0B", respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f47b3-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="f47b3-116">`BigInt` literais em Q # são idênticas às cadeias de caracteres inteiros grandes no .NET, com um "l" ou "L" à direita.</span><span class="sxs-lookup"><span data-stu-id="f47b3-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="f47b3-117">Há suporte para inteiros grandes hexadecimais com um prefixo "0x".</span><span class="sxs-lookup"><span data-stu-id="f47b3-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="f47b3-118">Portanto, veja a seguir todos os usos válidos de `BigInt` literais:</span><span class="sxs-lookup"><span data-stu-id="f47b3-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="f47b3-119">os literais `Double` em Q # são idênticos aos literais C#duplos no, exceto pelo fato de que nenhum "d" ou "d" à direita é necessário (ou permitido).</span><span class="sxs-lookup"><span data-stu-id="f47b3-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="f47b3-120">Dada uma expressão de matriz de qualquer tipo de elemento, uma expressão `Int` pode ser formada usando a função interna `Length`, com a expressão de matriz entre parênteses, `(` e `)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="f47b3-121">Por exemplo, se `a` estiver associado a uma matriz, `Length(a)` será uma expressão de número inteiro.</span><span class="sxs-lookup"><span data-stu-id="f47b3-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="f47b3-122">Se `b` for uma matriz de matrizes de inteiros, `Int[][]`, `Length(b)` será o número de submatrizes em `b`e `Length(b[1])` será o número de inteiros na segunda submatriz em `b`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="f47b3-123">Dadas duas expressões numéricas do mesmo tipo, os operadores binários `+`, `-`, `*`e `/` podem ser usados para formar uma nova expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="f47b3-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="f47b3-124">O tipo da nova expressão será o mesmo que os tipos das expressões constituintes.</span><span class="sxs-lookup"><span data-stu-id="f47b3-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="f47b3-125">Dadas duas expressões de inteiro, o operador binário `^` (Power) pode ser usado para formar uma nova expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="f47b3-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="f47b3-126">Da mesma forma, `^` pode ser usado com duas expressões Double para formar uma nova expressão Double.</span><span class="sxs-lookup"><span data-stu-id="f47b3-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="f47b3-127">Por fim, `^` pode ser usado com um inteiro grande à esquerda e um inteiro à direita para formar uma nova expressão de inteiro grande.</span><span class="sxs-lookup"><span data-stu-id="f47b3-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="f47b3-128">Nesse caso, o segundo parâmetro deve caber em 32 bits; caso contrário, um erro de tempo de execução será gerado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="f47b3-129">Dadas duas expressões de inteiro ou de inteiro grande, um novo inteiro ou uma expressão de inteiro grande podem ser formados usando os operadores `%` (módulo), `&&&` (bit e), `|||` (bit-a-or) ou `^^^` ("XOR bit)".</span><span class="sxs-lookup"><span data-stu-id="f47b3-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="f47b3-130">Dado um inteiro ou uma expressão de inteiro grande à esquerda e uma expressão de inteiro à direita, os operadores de `<<<` (deslocamento aritmético à esquerda) ou `>>>` (deslocamento aritmético à direita) podem ser usados para criar uma nova expressão com o mesmo tipo que a do lado esquerdo expressão.</span><span class="sxs-lookup"><span data-stu-id="f47b3-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="f47b3-131">O segundo parâmetro (o valor de deslocamento) para a operação de deslocamento deve ser maior ou igual a zero; o comportamento para valores de deslocamento negativos é indefinido.</span><span class="sxs-lookup"><span data-stu-id="f47b3-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="f47b3-132">O valor de deslocamento para uma das operações de deslocamento também deve se ajustar a 32 bits; caso contrário, um erro de tempo de execução será gerado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="f47b3-133">Se o número a ser deslocado for um inteiro, o valor de deslocamento será interpretado `mod 64`; ou seja, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="f47b3-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="f47b3-134">Para os valores inteiros e inteiros grandes, as turnos são aritméticas.</span><span class="sxs-lookup"><span data-stu-id="f47b3-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="f47b3-135">A mudança de um valor negativo para a esquerda ou direita resultará em um número negativo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="f47b3-136">Ou seja, mudar uma etapa para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f47b3-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="f47b3-137">Divisão de inteiros e módulo de inteiro seguem o mesmo comportamento de números C#negativos.</span><span class="sxs-lookup"><span data-stu-id="f47b3-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="f47b3-138">Ou seja, `a % b` sempre terá o mesmo sinal que `a`e `b * (a / b) + a % b` sempre será igual `a`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="f47b3-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f47b3-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="f47b3-140">5</span><span class="sxs-lookup"><span data-stu-id="f47b3-140">5</span></span> | <span data-ttu-id="f47b3-141">2</span><span class="sxs-lookup"><span data-stu-id="f47b3-141">2</span></span> | <span data-ttu-id="f47b3-142">2</span><span class="sxs-lookup"><span data-stu-id="f47b3-142">2</span></span> | <span data-ttu-id="f47b3-143">1</span><span class="sxs-lookup"><span data-stu-id="f47b3-143">1</span></span>
 <span data-ttu-id="f47b3-144">5</span><span class="sxs-lookup"><span data-stu-id="f47b3-144">5</span></span> | <span data-ttu-id="f47b3-145">-2</span><span class="sxs-lookup"><span data-stu-id="f47b3-145">-2</span></span> | <span data-ttu-id="f47b3-146">-2</span><span class="sxs-lookup"><span data-stu-id="f47b3-146">-2</span></span> | <span data-ttu-id="f47b3-147">1</span><span class="sxs-lookup"><span data-stu-id="f47b3-147">1</span></span>
 <span data-ttu-id="f47b3-148">-5</span><span class="sxs-lookup"><span data-stu-id="f47b3-148">-5</span></span> | <span data-ttu-id="f47b3-149">2</span><span class="sxs-lookup"><span data-stu-id="f47b3-149">2</span></span> | <span data-ttu-id="f47b3-150">-2</span><span class="sxs-lookup"><span data-stu-id="f47b3-150">-2</span></span> | <span data-ttu-id="f47b3-151">-1</span><span class="sxs-lookup"><span data-stu-id="f47b3-151">-1</span></span>
 <span data-ttu-id="f47b3-152">-5</span><span class="sxs-lookup"><span data-stu-id="f47b3-152">-5</span></span> | <span data-ttu-id="f47b3-153">-2</span><span class="sxs-lookup"><span data-stu-id="f47b3-153">-2</span></span> | <span data-ttu-id="f47b3-154">2</span><span class="sxs-lookup"><span data-stu-id="f47b3-154">2</span></span> | <span data-ttu-id="f47b3-155">-1</span><span class="sxs-lookup"><span data-stu-id="f47b3-155">-1</span></span>

<span data-ttu-id="f47b3-156">Divisão de inteiro grande e módulo funciona da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="f47b3-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="f47b3-157">Dada qualquer expressão numérica, uma nova expressão pode ser formada usando o operador unário `-`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="f47b3-158">A nova expressão será o mesmo tipo da expressão constituinte.</span><span class="sxs-lookup"><span data-stu-id="f47b3-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="f47b3-159">Dado qualquer inteiro ou expressão de inteiro grande, uma nova expressão do mesmo tipo pode ser formada usando o operador unário `~~~` (complemento bit-a).</span><span class="sxs-lookup"><span data-stu-id="f47b3-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="f47b3-160">Expressões booleanas</span><span class="sxs-lookup"><span data-stu-id="f47b3-160">Boolean Expressions</span></span>

<span data-ttu-id="f47b3-161">Os dois `Bool` valores literais são `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="f47b3-162">Dadas as duas expressões do mesmo tipo primitivo, os operadores binários `==` e `!=` podem ser usados para construir uma expressão de `Bool`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="f47b3-163">A expressão será true se as duas expressões forem (resp. is not) iguais.</span><span class="sxs-lookup"><span data-stu-id="f47b3-163">The expression will be true if the two expressions are (resp. are not) equal.</span></span>

<span data-ttu-id="f47b3-164">Os valores de tipos definidos pelo usuário não podem ser comparados, apenas seus valores podem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="f47b3-164">Values of user-defined types may not be compared, only their values can be compared.</span></span> <span data-ttu-id="f47b3-165">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="f47b3-165">For example,</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="f47b3-166">A comparação de igualdade para valores de `Qubit` é igualdade de identidade; ou seja, se as duas expressões identificam o mesmo qubit.</span><span class="sxs-lookup"><span data-stu-id="f47b3-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="f47b3-167">O estado dos dois qubits não são comparados, acessados, medidos ou modificados por essa comparação.</span><span class="sxs-lookup"><span data-stu-id="f47b3-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="f47b3-168">A comparação de igualdade para valores de `Double` pode ser enganosa devido a efeitos de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="f47b3-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="f47b3-169">Por exemplo, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="f47b3-170">Dadas quaisquer duas expressões numéricas, os operadores binários `>`, `<`, `>=`e `<=` podem ser usados para construir uma nova expressão booliana que seja verdadeira se a primeira expressão for maior que, menor que, maior ou igual a ou menor ou igual à segunda expressão.</span><span class="sxs-lookup"><span data-stu-id="f47b3-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="f47b3-171">Dadas quaisquer duas expressões booleanas, os operadores binários `and` e `or` podem ser usados para construir uma nova expressão booliana que seja verdadeira se ambos (resp. ou ambos) as duas expressões forem true.</span><span class="sxs-lookup"><span data-stu-id="f47b3-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="f47b3-172">Dada qualquer expressão booliana, o operador unário `not` pode ser usado para construir uma nova expressão booliana que seja verdadeira se a expressão constituinte for falsa.</span><span class="sxs-lookup"><span data-stu-id="f47b3-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="f47b3-173">Expressões de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f47b3-173">String Expressions</span></span>

<span data-ttu-id="f47b3-174">Q # permite que as cadeias de caracteres sejam usadas na instrução `fail` e na função padrão `Log`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="f47b3-175">Cadeias de caracteres em Q # são literais ou cadeias de caracteres interpoladas.</span><span class="sxs-lookup"><span data-stu-id="f47b3-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="f47b3-176">Literais de cadeia de caracteres são semelhantes a literais de cadeia de caracteres simples na maioria dos idiomas: uma sequência de caracteres Unicode entre aspas duplas, `"`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="f47b3-177">Dentro de uma cadeia de caracteres, o caractere de barra invertida `\` pode ser usado para escapar de um caractere de aspas duplas e para inserir uma linha nova como `\n`, um retorno de carro como `\r`e uma tabulação como `\t`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="f47b3-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f47b3-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="f47b3-179">A sintaxe de Q # para interpolações de cadeia de caracteres é C# um subconjunto da sintaxe 7,0; Q # não oferece suporte a cadeias de caracteres interpoladas (várias linhas) textuais.</span><span class="sxs-lookup"><span data-stu-id="f47b3-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="f47b3-180">Consulte [*cadeias de caracteres interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) para a C# sintaxe.</span><span class="sxs-lookup"><span data-stu-id="f47b3-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="f47b3-181">As expressões dentro de uma cadeia de caracteres interpolada seguem a sintaxe C# de Q #, não a sintaxe.</span><span class="sxs-lookup"><span data-stu-id="f47b3-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="f47b3-182">Qualquer expressão Q # válida pode aparecer em uma cadeia de caracteres interpolada.</span><span class="sxs-lookup"><span data-stu-id="f47b3-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="f47b3-183">Expressões qubit</span><span class="sxs-lookup"><span data-stu-id="f47b3-183">Qubit Expressions</span></span>

<span data-ttu-id="f47b3-184">As únicas `Qubit` expressões são símbolos associados a valores de `Qubit` ou elementos de matriz de matrizes de `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="f47b3-185">Não há literais `Qubit`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="f47b3-186">Expressões Pauli</span><span class="sxs-lookup"><span data-stu-id="f47b3-186">Pauli Expressions</span></span>

<span data-ttu-id="f47b3-187">Os quatro valores `Pauli`, `PauliI`, `PauliX`, `PauliY`e `PauliZ`, são todas as expressões de `Pauli` válidas.</span><span class="sxs-lookup"><span data-stu-id="f47b3-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="f47b3-188">Além disso, as únicas expressões `Pauli` são símbolos associados a valores de `Pauli` ou elementos de matriz de matrizes de `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="f47b3-189">Expressões de resultado</span><span class="sxs-lookup"><span data-stu-id="f47b3-189">Result Expressions</span></span>

<span data-ttu-id="f47b3-190">Os dois valores `Result`, `One` e `Zero`, são expressões de `Result` válidas.</span><span class="sxs-lookup"><span data-stu-id="f47b3-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="f47b3-191">Além disso, as únicas expressões `Result` são símbolos associados a valores de `Result` ou elementos de matriz de matrizes de `Result`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="f47b3-192">Em particular, observe que `One` não é o mesmo que o inteiro `1`, e não há nenhuma conversão direta entre eles.</span><span class="sxs-lookup"><span data-stu-id="f47b3-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="f47b3-193">O mesmo é verdadeiro para `Zero` e `0`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="f47b3-194">Expressões de intervalo</span><span class="sxs-lookup"><span data-stu-id="f47b3-194">Range Expressions</span></span>

<span data-ttu-id="f47b3-195">Dadas as três expressões de `Int` `start`, `step`e `stop`, `start .. step .. stop` é uma expressão de intervalo cujo primeiro elemento é `start`, o segundo elemento é `start+step`, o terceiro elemento é `start+step+step`, etc., até que `stop` seja passado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="f47b3-196">Um intervalo pode estar vazio se, por exemplo, `step` for positivo e `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="f47b3-197">O último elemento do intervalo será `stop` se a diferença entre `start` e `stop` for um múltiplo integral de `step`; ou seja, o intervalo é inclusivo em ambas as extremidades.</span><span class="sxs-lookup"><span data-stu-id="f47b3-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="f47b3-198">Dadas quaisquer duas expressões `Int` `start` e `stop`, `start .. stop` é uma expressão de intervalo que é igual a `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="f47b3-199">Observe que a `step` implícita é + 1, mesmo se `stop` for menor que `start`; Nesse caso, o intervalo está vazio.</span><span class="sxs-lookup"><span data-stu-id="f47b3-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="f47b3-200">Alguns intervalos de exemplo são:</span><span class="sxs-lookup"><span data-stu-id="f47b3-200">Some example ranges are:</span></span>

- <span data-ttu-id="f47b3-201">`1..3` é o intervalo 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="f47b3-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="f47b3-202">`2..2..5` é o intervalo de 2, 4.</span><span class="sxs-lookup"><span data-stu-id="f47b3-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="f47b3-203">`2..2..6` é o intervalo de 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="f47b3-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="f47b3-204">`6..-2..2` é o intervalo de 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="f47b3-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="f47b3-205">`2..1` é o intervalo vazio.</span><span class="sxs-lookup"><span data-stu-id="f47b3-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="f47b3-206">`2..6..7` é o intervalo 2.</span><span class="sxs-lookup"><span data-stu-id="f47b3-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="f47b3-207">`2..2..1` é o intervalo vazio.</span><span class="sxs-lookup"><span data-stu-id="f47b3-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="f47b3-208">`1..-1..2` é o intervalo vazio.</span><span class="sxs-lookup"><span data-stu-id="f47b3-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="f47b3-209">Expressões que podem ser chamadas</span><span class="sxs-lookup"><span data-stu-id="f47b3-209">Callable Expressions</span></span>

<span data-ttu-id="f47b3-210">Um literal que pôde ser chamado é o nome de uma operação ou função definida no escopo de compilação.</span><span class="sxs-lookup"><span data-stu-id="f47b3-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="f47b3-211">Por exemplo, `X` é um literal de operação que se refere à operação de `X` de biblioteca padrão e `Message` é um literal de função que se refere à função de `Message` de biblioteca padrão.</span><span class="sxs-lookup"><span data-stu-id="f47b3-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="f47b3-212">Se uma operação der suporte ao `Adjoint` functor, `Adjoint op` será uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="f47b3-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="f47b3-213">Da mesma forma, se a operação der suporte ao `Controlled` functor, `Controlled op` será uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="f47b3-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="f47b3-214">Os tipos dessas expressões são especificados em [transmissão functors](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="f47b3-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="f47b3-215">Transmissão functors (`Adjoint` e `Controlled`) são associados mais de mais de todos os outros operadores, exceto para o operador de desencapsulamento `!` e a indexação de matriz com `[]`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="f47b3-216">Portanto, as seguintes são todas legais, supondo que as operações suportam o transmissão functors usado:</span><span class="sxs-lookup"><span data-stu-id="f47b3-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="f47b3-217">Um literal resgatável pode ser usado como um valor, digamos para atribuir a uma variável ou passar para outro callable.</span><span class="sxs-lookup"><span data-stu-id="f47b3-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="f47b3-218">Nesse caso, se o callable tiver parâmetros de tipo, eles deverão ser fornecidos como parte do valor que pode ser chamado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="f47b3-219">Um valor callable não pode ter nenhum parâmetro de tipo não especificado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="f47b3-220">Por exemplo, se `Fun` for uma função com assinatura `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="f47b3-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="f47b3-221">Expressões de invocação que podem ser chamadas</span><span class="sxs-lookup"><span data-stu-id="f47b3-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="f47b3-222">Dada uma expressão resgatável (operação ou função) e uma expressão de tupla do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada acrescentando-se a expressão de tupla à expressão que pode ser chamada.</span><span class="sxs-lookup"><span data-stu-id="f47b3-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="f47b3-223">O tipo da expressão de invocação é o tipo de saída da assinatura do callable.</span><span class="sxs-lookup"><span data-stu-id="f47b3-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="f47b3-224">Por exemplo, se `Op` for uma operação com assinatura `((Int, Qubit) => Double)`, `Op(3, qubit1)` será uma expressão do tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="f47b3-225">Da mesma forma, se `Sin` for uma função com assinatura `(Double -> Double)`, `Sin(0.1)` será uma expressão do tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="f47b3-226">Por fim, se `Builder` for uma função com assinatura `(Int -> (Int -> Int))`, `Builder(3)` será uma função de em para int.</span><span class="sxs-lookup"><span data-stu-id="f47b3-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="f47b3-227">Invocar o resultado de uma expressão com valor callable requer um par extra de parênteses em volta da expressão callable.</span><span class="sxs-lookup"><span data-stu-id="f47b3-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="f47b3-228">Portanto, para invocar o resultado da chamada de `Builder` do parágrafo anterior, a sintaxe correta é:</span><span class="sxs-lookup"><span data-stu-id="f47b3-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="f47b3-229">Ao invocar um callable-parametrizado de tipo, os parâmetros de tipo reais podem ser especificados entre colchetes angulares `<` e `>` após a expressão que pode ser chamada.</span><span class="sxs-lookup"><span data-stu-id="f47b3-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="f47b3-230">Isso geralmente é desnecessário, pois o compilador Q # inferirá os tipos reais.</span><span class="sxs-lookup"><span data-stu-id="f47b3-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="f47b3-231">Ele é necessário para o aplicativo parcial (veja abaixo) se um argumento com parâmetros de tipo for deixado não especificado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="f47b3-232">Às vezes, também é útil ao passar operações com functor diferentes para um callable.</span><span class="sxs-lookup"><span data-stu-id="f47b3-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="f47b3-233">Por exemplo, se `Func` tiver assinatura `('T1, 'T2, 'T1) -> 'T2`, `Op1` e `Op2` têm assinatura `(Qubit[] => Unit is Adj)`e `Op3` tem `(Qubit[] => Unit)`de assinatura, para invocar `Func` com `Op1` como o primeiro argumento, `Op2` como o segundo e `Op3` como o terceiro:</span><span class="sxs-lookup"><span data-stu-id="f47b3-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="f47b3-234">A especificação de tipo é necessária porque `Op3` e `Op1` têm tipos diferentes, portanto o compilador tratará isso como ambíguo sem a especificação.</span><span class="sxs-lookup"><span data-stu-id="f47b3-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="f47b3-235">Aplicativo parcial</span><span class="sxs-lookup"><span data-stu-id="f47b3-235">Partial Application</span></span>

<span data-ttu-id="f47b3-236">Dada uma expressão resgatável, um novo callable pode ser criado fornecendo um subconjunto dos argumentos para o callable.</span><span class="sxs-lookup"><span data-stu-id="f47b3-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="f47b3-237">Isso é chamado de _aplicativo parcial_.</span><span class="sxs-lookup"><span data-stu-id="f47b3-237">This is called _partial application_.</span></span>

<span data-ttu-id="f47b3-238">Em Q #, um resgatável aplicado parcialmente é expresso escrevendo uma expressão de invocação normal, mas usando um sublinhado, `_`, para os argumentos não especificados.</span><span class="sxs-lookup"><span data-stu-id="f47b3-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="f47b3-239">O callable que resultau tem o mesmo tipo de resultado que o callable de base, e as mesmas especializações para operações.</span><span class="sxs-lookup"><span data-stu-id="f47b3-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="f47b3-240">O tipo de entrada do aplicativo parcial é simplesmente o tipo original com os argumentos especificados removidos.</span><span class="sxs-lookup"><span data-stu-id="f47b3-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="f47b3-241">Se uma variável mutável for passada como um argumento especificado ao criar um aplicativo parcial, o valor atual da variável será usado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="f47b3-242">Alterar o valor da variável subsequentemente não afetará o aplicativo parcial.</span><span class="sxs-lookup"><span data-stu-id="f47b3-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="f47b3-243">Por exemplo, se `Op` tiver tipo `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="f47b3-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="f47b3-244">`Op(5,(_,_))` tem `(((Qubit,Qubit), Double) => Unit is Adj)`de tipo e, portanto, tem `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="f47b3-245">`Op(_,(_,1.0))` tem `((Int, (Qubit,Qubit)) => Unit is Adj)`de tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="f47b3-246">`Op(_,((q1,q2),_))` tem `((Int,Double) => Unit is Adj)`de tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="f47b3-247">Observe que aplicamos a equivalência de tupla singleton aqui.</span><span class="sxs-lookup"><span data-stu-id="f47b3-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="f47b3-248">Se o chamado parcialmente aplicado tiver parâmetros de tipo que não podem ser inferidos pelo compilador, eles deverão ser fornecidos no site de invocação.</span><span class="sxs-lookup"><span data-stu-id="f47b3-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="f47b3-249">O aplicativo parcial não pode ter nenhum parâmetro de tipo não especificado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="f47b3-250">Por exemplo, se `Op` tiver tipo `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="f47b3-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="f47b3-251">Recursão</span><span class="sxs-lookup"><span data-stu-id="f47b3-251">Recursion</span></span>

<span data-ttu-id="f47b3-252">Os chamadores do Q # podem ser recursivos direta ou indiretamente.</span><span class="sxs-lookup"><span data-stu-id="f47b3-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="f47b3-253">Ou seja, uma operação ou função pode chamar a si mesma ou chamar outro callable que chama direta ou indiretamente a operação que pode ser chamada.</span><span class="sxs-lookup"><span data-stu-id="f47b3-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="f47b3-254">No entanto, há dois comentários importantes sobre o uso da recursão:</span><span class="sxs-lookup"><span data-stu-id="f47b3-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="f47b3-255">O uso da recursão nas operações provavelmente interfere em determinadas otimizações.</span><span class="sxs-lookup"><span data-stu-id="f47b3-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="f47b3-256">Isso pode ter um impacto significativo no tempo de execução do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="f47b3-257">Ao executar em um dispositivo Quantum real, o espaço de pilha pode ser limitado e, portanto, a recursão profunda pode levar a um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f47b3-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="f47b3-258">Em particular, o compilador e o tempo de execução do Q # não identificam e otimizam a recursão da cauda.</span><span class="sxs-lookup"><span data-stu-id="f47b3-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="f47b3-259">Expressões de tupla</span><span class="sxs-lookup"><span data-stu-id="f47b3-259">Tuple Expressions</span></span>

<span data-ttu-id="f47b3-260">Um literal de tupla é uma sequência de expressões de elemento do tipo apropriado, separadas por vírgulas, delimitadas em `(` e `)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="f47b3-261">Por exemplo, `(1, One)` é uma expressão de `(Int, Result)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="f47b3-262">Além de literais, as únicas expressões de tupla são símbolos associados a valores de tupla, elementos de matriz de matrizes de tupla e invocações que retornam tuplas.</span><span class="sxs-lookup"><span data-stu-id="f47b3-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="f47b3-263">Expressões de tipo definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f47b3-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="f47b3-264">Um literal de um tipo definido pelo usuário consiste no nome do tipo seguido por um literal de tupla do tipo de tupla base do tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="f47b3-265">Por exemplo, se `IntPair` for um tipo definido pelo usuário com base em `(Int, Int)`, `IntPair(2,3)` seria um literal válido desse tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="f47b3-266">Além de literais, as únicas expressões de um tipo definido pelo usuário são símbolos que são associados a valores desse tipo, elementos da matriz de matrizes desse tipo e invocações que retornam esse tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="f47b3-267">Desencapsular expressões</span><span class="sxs-lookup"><span data-stu-id="f47b3-267">Unwrap Expressions</span></span>

<span data-ttu-id="f47b3-268">Em Q #, o operador de desencapsulamento é um ponto de exclamação à direita `!`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="f47b3-269">Por exemplo, se `IntPair` for um tipo definido pelo usuário com o tipo subjacente `(Int, Int)`e `s` for uma variável com o valor `IntPair(2,3)`, `s!` seria `(2,3)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="f47b3-270">Para tipos definidos pelo usuário definidos em termos de outros tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f47b3-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="f47b3-271">o operador de desencapsulamento pode ser repetido; por exemplo, `s!!` indica o valor duplo desencapsulado de `s`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="f47b3-272">Portanto, se `WrappedPair` for um tipo definido pelo usuário com o tipo subjacente `IntPair`e `t` for uma variável com o valor `WrappedPair(IntPair(1,2))`, `t!!` seria `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="f47b3-273">O operador de `!` tem precedência mais alta do que todos os outros operadores diferentes de `[]` para indexação e divisão de matriz.</span><span class="sxs-lookup"><span data-stu-id="f47b3-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="f47b3-274">`!` e `[]` associar à posição; ou seja, `a[i]![3]` deve ser lido como `((a[i])!)[3]`: Pegue o elemento `i`' th de `a`, desenvolva-o e, em seguida, obtenha o terceiro elemento do valor não encapsulado (que deve ser uma matriz).</span><span class="sxs-lookup"><span data-stu-id="f47b3-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="f47b3-275">A precedência do operador de `!` tem um impacto que pode não ser óbvio.</span><span class="sxs-lookup"><span data-stu-id="f47b3-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="f47b3-276">Se uma função ou operação retorna um valor que, em seguida, é desencapsulada, a função ou a chamada de operação deve ser colocada entre parênteses para que a tupla de argumento seja associada à chamada em vez de ser desencapsulada.</span><span class="sxs-lookup"><span data-stu-id="f47b3-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="f47b3-277">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f47b3-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="f47b3-278">Expressões de matriz</span><span class="sxs-lookup"><span data-stu-id="f47b3-278">Array Expressions</span></span>

<span data-ttu-id="f47b3-279">Um literal de matriz é uma sequência de uma ou mais expressões de elemento, separadas por vírgulas, delimitadas em `[` e `]`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="f47b3-280">Todos os elementos devem ser compatíveis com o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="f47b3-281">Se o tipo de elemento comum for uma operação ou tipo de função, todos os elementos deverão ter os mesmos tipos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="f47b3-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="f47b3-282">O tipo de elemento da matriz dará suporte a qualquer transmissão functors que tenha suporte de todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="f47b3-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="f47b3-283">Por exemplo, se `Op1`, `Op2`e `Op3` todos são `Qubit[] => Unit`, mas `Op1` dá suporte a `Adjoint`, `Op2` dá suporte a `Controlled`e `Op3` dá suporte a:</span><span class="sxs-lookup"><span data-stu-id="f47b3-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="f47b3-284">`[Op1, Op2]` é uma matriz de operações de `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="f47b3-285">`[Op1, Op3]` é uma matriz de operações de `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="f47b3-286">`[Op2, Op3]` é uma matriz de operações de `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="f47b3-287">Literais de matriz vazios, `[]`, não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f47b3-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="f47b3-288">Em vez disso, usando `new ★[0]`, em que `★` é um espaço reservado para um tipo adequado, permite criar a matriz desejada de comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="f47b3-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="f47b3-289">Dadas duas matrizes do mesmo tipo, o operador binário `+` pode ser usado para formar uma nova matriz que é a concatenação das duas matrizes.</span><span class="sxs-lookup"><span data-stu-id="f47b3-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="f47b3-290">Por exemplo, `[1,2,3] + [4,5,6]` é `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="f47b3-291">Criação de matriz</span><span class="sxs-lookup"><span data-stu-id="f47b3-291">Array Creation</span></span>

<span data-ttu-id="f47b3-292">Dado um tipo e uma expressão `Int`, o operador `new` pode ser usado para alocar uma nova matriz do tamanho determinado.</span><span class="sxs-lookup"><span data-stu-id="f47b3-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="f47b3-293">Por exemplo, `new Int[i+1]` alocaria uma nova matriz de `Int` com elementos `i+1`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="f47b3-294">Os elementos de uma nova matriz são inicializados para um valor padrão dependente de tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="f47b3-295">Na maioria dos casos, essa é uma variação de zero.</span><span class="sxs-lookup"><span data-stu-id="f47b3-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="f47b3-296">Para qubits e callableies, que são referências a entidades, não há nenhum valor padrão razoável.</span><span class="sxs-lookup"><span data-stu-id="f47b3-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="f47b3-297">Portanto, para esses tipos, o padrão é uma referência inválida que não pode ser usada sem causar um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f47b3-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="f47b3-298">Isso é semelhante a uma referência nula em linguagens como C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="f47b3-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="f47b3-299">As matrizes que contêm qubits ou callables devem ser inicializadas corretamente com valores não padrão antes que seus elementos possam ser usados com segurança.</span><span class="sxs-lookup"><span data-stu-id="f47b3-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="f47b3-300">Rotinas de inicialização adequadas podem ser encontradas em <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="f47b3-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="f47b3-301">Os valores padrão para cada tipo são:</span><span class="sxs-lookup"><span data-stu-id="f47b3-301">The default values for each type are:</span></span>

<span data-ttu-id="f47b3-302">Tipo</span><span class="sxs-lookup"><span data-stu-id="f47b3-302">Type</span></span> | <span data-ttu-id="f47b3-303">Predefinição</span><span class="sxs-lookup"><span data-stu-id="f47b3-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="f47b3-304">_qubit inválido_</span><span class="sxs-lookup"><span data-stu-id="f47b3-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="f47b3-305">O intervalo vazio, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="f47b3-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="f47b3-306">_callable inválido_</span><span class="sxs-lookup"><span data-stu-id="f47b3-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="f47b3-307">Os tipos de tupla são inicializados elemento por elemento.</span><span class="sxs-lookup"><span data-stu-id="f47b3-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="f47b3-308">Matrizes denteadas</span><span class="sxs-lookup"><span data-stu-id="f47b3-308">Jagged Arrays</span></span>

<span data-ttu-id="f47b3-309">Uma matriz denteada, às vezes chamada de "matriz de matrizes", é uma matriz cujos elementos são matrizes.</span><span class="sxs-lookup"><span data-stu-id="f47b3-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="f47b3-310">Os elementos de uma matriz denteada podem ser de tamanhos diferentes.</span><span class="sxs-lookup"><span data-stu-id="f47b3-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="f47b3-311">O exemplo a seguir mostra como declarar e inicializar uma matriz denteada que representa uma tabela de multiplicação.</span><span class="sxs-lookup"><span data-stu-id="f47b3-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="f47b3-312">Fatias de matriz</span><span class="sxs-lookup"><span data-stu-id="f47b3-312">Array Slices</span></span>

<span data-ttu-id="f47b3-313">Dada uma expressão de matriz e uma expressão de `Range`, uma nova expressão pode ser formada usando o `[` e `]` operador de fatia de matriz.</span><span class="sxs-lookup"><span data-stu-id="f47b3-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="f47b3-314">A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range`, na ordem definida pelo `Range`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="f47b3-315">Por exemplo, se `a` estiver associado a uma matriz de `Double`s, `a[3..-1..0]` será uma expressão de `Double[]` que contém os quatro primeiros elementos de `a`, mas na ordem inversa, como aparecem no `a`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="f47b3-316">Se o `Range` estiver vazio, a fatia da matriz resultante será de comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="f47b3-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="f47b3-317">Se a expressão de matriz não for um identificador simples, ela deverá ser colocada entre parênteses, para fatiar.</span><span class="sxs-lookup"><span data-stu-id="f47b3-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="f47b3-318">Por exemplo, se `a` e `b` forem matrizes de `Int`s, uma fatia da concatenação seria expressa como:</span><span class="sxs-lookup"><span data-stu-id="f47b3-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="f47b3-319">Todas as matrizes em Q # são baseadas em zero.</span><span class="sxs-lookup"><span data-stu-id="f47b3-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="f47b3-320">Ou seja, o primeiro elemento de uma matriz `a` sempre é `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="f47b3-321">A partir da nossa versão 0,8, damos suporte a expressões contextuais para divisão de intervalo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="f47b3-322">Em particular, os valores de início e término do intervalo podem ser omitidos no contexto de uma expressão de divisão do intervalo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="f47b3-323">Nesse caso, o compilador aplicará as regras a seguir para inferir os delimitadores pretendidos para o intervalo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="f47b3-324">Por exemplo, se o valor de início do intervalo for omitido, o valor inicial inferido</span><span class="sxs-lookup"><span data-stu-id="f47b3-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="f47b3-325">será zero se nenhuma etapa for especificada ou a etapa especificada for positiva e</span><span class="sxs-lookup"><span data-stu-id="f47b3-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="f47b3-326">é o comprimento da matriz segmentada menos uma se a etapa especificada for negativa.</span><span class="sxs-lookup"><span data-stu-id="f47b3-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="f47b3-327">Se o valor final do intervalo for omitido, o valor final inferido</span><span class="sxs-lookup"><span data-stu-id="f47b3-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="f47b3-328">é o comprimento da matriz segmentada menos uma se nenhuma etapa for especificada ou a etapa especificada for positiva e</span><span class="sxs-lookup"><span data-stu-id="f47b3-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="f47b3-329">será zero se a etapa especificada for negativa.</span><span class="sxs-lookup"><span data-stu-id="f47b3-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="f47b3-330">Expressões de elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="f47b3-330">Array Element Expressions</span></span>

<span data-ttu-id="f47b3-331">Dada uma expressão de matriz e uma expressão de `Int`, uma nova expressão pode ser formada usando o `[` e `]` operador de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="f47b3-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="f47b3-332">A nova expressão será do mesmo tipo que o tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="f47b3-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="f47b3-333">Por exemplo, se `a` estiver associado a uma matriz de `Double`s, `a[4]` será uma expressão de `Double`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="f47b3-334">Se a expressão de matriz não for um identificador simples, ela deverá ser colocada entre parênteses para selecionar um elemento.</span><span class="sxs-lookup"><span data-stu-id="f47b3-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="f47b3-335">Por exemplo, se `a` e `b` forem matrizes de `Int`s, um elemento da concatenação seria expresso como:</span><span class="sxs-lookup"><span data-stu-id="f47b3-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="f47b3-336">Todas as matrizes em Q # são baseadas em zero.</span><span class="sxs-lookup"><span data-stu-id="f47b3-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="f47b3-337">Ou seja, o primeiro elemento de uma matriz `a` sempre é `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="f47b3-338">Expressões Copy-and-Update</span><span class="sxs-lookup"><span data-stu-id="f47b3-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="f47b3-339">Novas matrizes podem ser criadas a partir de existentes por meio de expressões de copiar e atualizar.</span><span class="sxs-lookup"><span data-stu-id="f47b3-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="f47b3-340">Uma expressão de copiar e atualizar é uma expressão do formulário `expression1 w/ expression2 <- expression3`, em que `expression1` deve ser do tipo `T[]` para algum `T`de tipo.</span><span class="sxs-lookup"><span data-stu-id="f47b3-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="f47b3-341">O segundo `expression2` define os índices dos elementos a serem modificados em comparação com a matriz em `expression1` e deve ser do tipo `Int` ou do tipo `Range`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="f47b3-342">Se `expression2` for do tipo `Int`, `expression3` terá que ser do tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="f47b3-343">Se `expression2` for do tipo `Range`, `expression3` terá que ser do tipo `T[]`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="f47b3-344">Uma expressão de copiar e atualizar `arr w/ idx <- value` constrói uma nova matriz com todos os elementos definidos para o elemento correspondente no `arr`, exceto para os elementos em `idx`, que são definidos como os que estão em `value`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="f47b3-345">Por exemplo, se `arr` contiver uma matriz `[0,1,2,3]`, então</span><span class="sxs-lookup"><span data-stu-id="f47b3-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="f47b3-346">`arr w/ 0 <- 10` é a `[10,1,2,3]`de matriz.</span><span class="sxs-lookup"><span data-stu-id="f47b3-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="f47b3-347">`arr w/ 2 <- 10` é a `[0,1,10,3]`de matriz.</span><span class="sxs-lookup"><span data-stu-id="f47b3-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="f47b3-348">`arr w/ 0..2..3 <- [10,12]` é a `[10,1,12,3]`de matriz.</span><span class="sxs-lookup"><span data-stu-id="f47b3-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="f47b3-349">Existem expressões semelhantes para itens nomeados em tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f47b3-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="f47b3-350">Considere, por exemplo, o tipo</span><span class="sxs-lookup"><span data-stu-id="f47b3-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="f47b3-351">Se `c` contiver o valor do tipo `Complex(1.,-1.)`, `c w/ Re <- 0.` será uma expressão do tipo `Complex` que é avaliada como `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="f47b3-352">Expressões condicionais</span><span class="sxs-lookup"><span data-stu-id="f47b3-352">Conditional Expressions</span></span>

<span data-ttu-id="f47b3-353">Dadas duas outras expressões do mesmo tipo e uma expressão booliana, a expressão condicional pode ser formada usando o ponto de interrogação `?` e a barra vertical `|`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="f47b3-354">Por exemplo, `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="f47b3-355">Neste exemplo, o valor da expressão condicional será `c` se `a==b` for true e `d` se for false.</span><span class="sxs-lookup"><span data-stu-id="f47b3-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="f47b3-356">As duas expressões podem ser avaliadas como operações que têm as mesmas entradas e saídas, mas dão suporte a diferentes transmissão functors.</span><span class="sxs-lookup"><span data-stu-id="f47b3-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="f47b3-357">Nesse caso, o tipo da expressão condicional é uma operação com as entradas e saídas que dão suporte a qualquer transmissão functors com suporte em ambas as expressões.</span><span class="sxs-lookup"><span data-stu-id="f47b3-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="f47b3-358">Por exemplo, se `Op1`, `Op2`e `Op3` todos são `Qubit[]=>Unit`, mas `Op1` dá suporte a `Adjoint`, `Op2` dá suporte a `Controlled`e `Op3` dá suporte a:</span><span class="sxs-lookup"><span data-stu-id="f47b3-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="f47b3-359">`flag ? Op1 | Op2` é uma operação `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="f47b3-360">`flag ? Op1 | Op3` é uma operação `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="f47b3-361">`flag ? Op2 | Op3` é uma operação `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="f47b3-362">Se qualquer uma das duas expressões de resultado possíveis incluir uma função ou uma chamada de operação, essa chamada só ocorrerá se o resultado for aquele que será o valor da chamada.</span><span class="sxs-lookup"><span data-stu-id="f47b3-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="f47b3-363">Por exemplo, no caso `a==b ? C(qs) | D(qs)`, se `a==b` for true, a operação de `C` será invocada e, se for false, somente `D` será invocada.</span><span class="sxs-lookup"><span data-stu-id="f47b3-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="f47b3-364">Isso é semelhante ao curto circuito em outras linguagens.</span><span class="sxs-lookup"><span data-stu-id="f47b3-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="f47b3-365">Precedência de operador</span><span class="sxs-lookup"><span data-stu-id="f47b3-365">Operator Precedence</span></span>

<span data-ttu-id="f47b3-366">Todos os operadores binários são associativos à direita, exceto para `^`.</span><span class="sxs-lookup"><span data-stu-id="f47b3-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="f47b3-367">Colchetes, `[` e `]`, para a divisão e a indexação de matriz, associe antes de qualquer operador.</span><span class="sxs-lookup"><span data-stu-id="f47b3-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="f47b3-368">O `Adjoint` transmissão functors e `Controlled` associado após a indexação da matriz, mas antes de todos os outros operadores.</span><span class="sxs-lookup"><span data-stu-id="f47b3-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="f47b3-369">Parênteses para operação e invocação de função também são associados antes de qualquer operador, mas após a indexação de matriz e transmissão functors.</span><span class="sxs-lookup"><span data-stu-id="f47b3-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="f47b3-370">Operadores em ordem de precedência, do mais alto ao mais baixo:</span><span class="sxs-lookup"><span data-stu-id="f47b3-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="f47b3-371">Operador</span><span class="sxs-lookup"><span data-stu-id="f47b3-371">Operator</span></span> | <span data-ttu-id="f47b3-372">Arity</span><span class="sxs-lookup"><span data-stu-id="f47b3-372">Arity</span></span> | <span data-ttu-id="f47b3-373">Descrição</span><span class="sxs-lookup"><span data-stu-id="f47b3-373">Description</span></span> | <span data-ttu-id="f47b3-374">Tipos de operando</span><span class="sxs-lookup"><span data-stu-id="f47b3-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="f47b3-375">`!` à direita</span><span class="sxs-lookup"><span data-stu-id="f47b3-375">trailing `!`</span></span> | <span data-ttu-id="f47b3-376">Unário</span><span class="sxs-lookup"><span data-stu-id="f47b3-376">Unary</span></span> | <span data-ttu-id="f47b3-377">Unwrap</span><span class="sxs-lookup"><span data-stu-id="f47b3-377">Unwrap</span></span> | <span data-ttu-id="f47b3-378">Qualquer tipo definido pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f47b3-378">Any user-defined type</span></span>
 <span data-ttu-id="f47b3-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="f47b3-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="f47b3-380">Unário</span><span class="sxs-lookup"><span data-stu-id="f47b3-380">Unary</span></span> | <span data-ttu-id="f47b3-381">Numérico negativo, complemento de bit-nte, negação lógica</span><span class="sxs-lookup"><span data-stu-id="f47b3-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="f47b3-382">`Int`, `BigInt` ou `Double` para `-`, `Int` ou `BigInt` para `~~~`, `Bool` para `not`</span><span class="sxs-lookup"><span data-stu-id="f47b3-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="f47b3-383">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-383">Binary</span></span> | <span data-ttu-id="f47b3-384">Potência de inteiro</span><span class="sxs-lookup"><span data-stu-id="f47b3-384">Integer power</span></span> | <span data-ttu-id="f47b3-385">`Int` ou `BigInt` para a base `Int` para o expoente</span><span class="sxs-lookup"><span data-stu-id="f47b3-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="f47b3-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="f47b3-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="f47b3-387">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-387">Binary</span></span> | <span data-ttu-id="f47b3-388">Divisão, multiplicação, módulo de inteiro</span><span class="sxs-lookup"><span data-stu-id="f47b3-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="f47b3-389">`Int`, `BigInt` ou `Double` para `/` e `*`, `Int` ou `BigInt` para `%`</span><span class="sxs-lookup"><span data-stu-id="f47b3-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="f47b3-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="f47b3-390">`+`, `-`</span></span> | <span data-ttu-id="f47b3-391">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-391">Binary</span></span> | <span data-ttu-id="f47b3-392">Adição ou concatenação de cadeia de caracteres e matriz, subtração</span><span class="sxs-lookup"><span data-stu-id="f47b3-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="f47b3-393">`Int`, `BigInt` ou `Double`, além de `String` ou qualquer tipo de matriz para `+`</span><span class="sxs-lookup"><span data-stu-id="f47b3-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="f47b3-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="f47b3-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="f47b3-395">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-395">Binary</span></span> | <span data-ttu-id="f47b3-396">Deslocamento à esquerda, deslocamento à direita</span><span class="sxs-lookup"><span data-stu-id="f47b3-396">Left shift, right shift</span></span> | <span data-ttu-id="f47b3-397">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="f47b3-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="f47b3-398">`<`, `<=`, `>``>=`</span><span class="sxs-lookup"><span data-stu-id="f47b3-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="f47b3-399">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-399">Binary</span></span> | <span data-ttu-id="f47b3-400">Comparações de menor que, menor que ou igual a, maior que, maior que ou igual a</span><span class="sxs-lookup"><span data-stu-id="f47b3-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="f47b3-401">`Int`, `BigInt` ou `Double`</span><span class="sxs-lookup"><span data-stu-id="f47b3-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="f47b3-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="f47b3-402">`==`, `!=`</span></span> | <span data-ttu-id="f47b3-403">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-403">Binary</span></span> | <span data-ttu-id="f47b3-404">comparações iguais, não iguais</span><span class="sxs-lookup"><span data-stu-id="f47b3-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="f47b3-405">qualquer tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="f47b3-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="f47b3-406">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-406">Binary</span></span> | <span data-ttu-id="f47b3-407">E</span><span class="sxs-lookup"><span data-stu-id="f47b3-407">Bitwise AND</span></span> | <span data-ttu-id="f47b3-408">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="f47b3-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="f47b3-409">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-409">Binary</span></span> | <span data-ttu-id="f47b3-410">XOR bits</span><span class="sxs-lookup"><span data-stu-id="f47b3-410">Bitwise XOR</span></span> | <span data-ttu-id="f47b3-411">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="f47b3-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="f47b3-412">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-412">Binary</span></span> | <span data-ttu-id="f47b3-413">OR-bit</span><span class="sxs-lookup"><span data-stu-id="f47b3-413">Bitwise OR</span></span> | <span data-ttu-id="f47b3-414">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="f47b3-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="f47b3-415">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-415">Binary</span></span> | <span data-ttu-id="f47b3-416">AND lógico</span><span class="sxs-lookup"><span data-stu-id="f47b3-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="f47b3-417">binário</span><span class="sxs-lookup"><span data-stu-id="f47b3-417">Binary</span></span> | <span data-ttu-id="f47b3-418">OR lógico</span><span class="sxs-lookup"><span data-stu-id="f47b3-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="f47b3-419">Binary/ternário</span><span class="sxs-lookup"><span data-stu-id="f47b3-419">Binary/Ternary</span></span> | <span data-ttu-id="f47b3-420">Operador de intervalo</span><span class="sxs-lookup"><span data-stu-id="f47b3-420">Range operator</span></span> | `Int`
 <span data-ttu-id="f47b3-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="f47b3-421">`?` `|`</span></span> | <span data-ttu-id="f47b3-422">Ternário</span><span class="sxs-lookup"><span data-stu-id="f47b3-422">Ternary</span></span> | <span data-ttu-id="f47b3-423">Condicional</span><span class="sxs-lookup"><span data-stu-id="f47b3-423">Conditional</span></span> | <span data-ttu-id="f47b3-424">`Bool` do lado esquerdo</span><span class="sxs-lookup"><span data-stu-id="f47b3-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="f47b3-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="f47b3-425">`w/` `<-`</span></span> | <span data-ttu-id="f47b3-426">Ternário</span><span class="sxs-lookup"><span data-stu-id="f47b3-426">Ternary</span></span> | <span data-ttu-id="f47b3-427">Copiar e atualizar</span><span class="sxs-lookup"><span data-stu-id="f47b3-427">Copy-and-update</span></span> | <span data-ttu-id="f47b3-428">consulte [expressões de copiar e atualizar](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="f47b3-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
