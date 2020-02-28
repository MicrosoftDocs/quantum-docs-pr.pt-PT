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
# <a name="expressions"></a><span data-ttu-id="c8c99-103">Expressões</span><span class="sxs-lookup"><span data-stu-id="c8c99-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="c8c99-104">Agrupamento</span><span class="sxs-lookup"><span data-stu-id="c8c99-104">Grouping</span></span>

<span data-ttu-id="c8c99-105">Dada qualquer expressão, essa mesma expressão em parênteses é uma expressão do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="c8c99-106">Por exemplo, `(7)` é uma expressão `Int`, `([1,2,3])` é uma expressão de tipo de matriz de `Int`s, e `((1,2))` é uma expressão com tipo `(Int, Int)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="c8c99-107">A equivalência entre valores simples e tuples de um único elemento descrito [no modelo](xref:microsoft.quantum.language.type-model#tuple-types) do tipo remove a ambiguidade entre `(6)` como um grupo e `(6)` como uma tuple de um único elemento.</span><span class="sxs-lookup"><span data-stu-id="c8c99-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="c8c99-108">Símbolos</span><span class="sxs-lookup"><span data-stu-id="c8c99-108">Symbols</span></span>

<span data-ttu-id="c8c99-109">O nome de um símbolo ligado ou atribuído a um valor de tipo `'T` é uma expressão de tipo `'T`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="c8c99-110">Por exemplo, se o símbolo `count` está ligado ao valor inteiro `5`, então `count` é uma expressão inteiro.</span><span class="sxs-lookup"><span data-stu-id="c8c99-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="c8c99-111">Expressões numéricas</span><span class="sxs-lookup"><span data-stu-id="c8c99-111">Numeric Expressions</span></span>

<span data-ttu-id="c8c99-112">Expressões numéricas são expressões de tipo `Int`, `BigInt`ou `Double`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="c8c99-113">Ou são números inteiros ou flutuantes.</span><span class="sxs-lookup"><span data-stu-id="c8c99-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="c8c99-114">`Int` literals em Q# são idênticos C#aos inteiros literais em , exceto que não é necessário seguir "l" ou "L" (ou permitido).</span><span class="sxs-lookup"><span data-stu-id="c8c99-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="c8c99-115">Os inteiros hexadecimais e binários são suportados com um prefixo "0x" e "0b", respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c8c99-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="c8c99-116">`BigInt` os literais em Q# são idênticos às grandes cordas de inteiro em .NET, com um "l" ou "L".</span><span class="sxs-lookup"><span data-stu-id="c8c99-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="c8c99-117">Os grandes inteiros hexadecimais são suportados com um prefixo "0x".</span><span class="sxs-lookup"><span data-stu-id="c8c99-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="c8c99-118">Assim, todos os seguintes usos válidos de `BigInt` literais:</span><span class="sxs-lookup"><span data-stu-id="c8c99-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="c8c99-119">`Double` literals em Q# são idênticos aos duplos literais em C#, exceto que não é necessário seguir "d" ou "D" (ou permitido).</span><span class="sxs-lookup"><span data-stu-id="c8c99-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="c8c99-120">Dada a expressão da matriz de qualquer tipo de elemento, pode formar-se uma expressão `Int` utilizando a função `Length` incorporada, com a expressão da matriz fechada em parênteses, `(` e `)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="c8c99-121">Por exemplo, se `a` está ligado a uma matriz, então `Length(a)` é uma expressão inteiro.</span><span class="sxs-lookup"><span data-stu-id="c8c99-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="c8c99-122">Se `b` é um conjunto de conjuntos de inteiros, `Int[][]`, então `Length(b)` é o número de sub-matrizes em `b`, e `Length(b[1])` é o número de inteiros na segunda sub-matriz em `b`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="c8c99-123">Tendo em conta duas expressões numéricas do mesmo tipo, os operadores binários `+`, `-`, `*`e `/` podem ser usados para formar uma nova expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="c8c99-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="c8c99-124">O tipo da nova expressão será o mesmo que os tipos das expressões constituintes.</span><span class="sxs-lookup"><span data-stu-id="c8c99-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="c8c99-125">Tendo em conta duas expressões inteiros, o operador binário `^` (potência) pode ser usado para formar uma nova expressão inteiro.</span><span class="sxs-lookup"><span data-stu-id="c8c99-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="c8c99-126">Da mesma forma, `^` pode ser usado com duas expressões duplas para formar uma nova expressão dupla.</span><span class="sxs-lookup"><span data-stu-id="c8c99-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="c8c99-127">Finalmente, `^` pode ser usado com um grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão inteiro.</span><span class="sxs-lookup"><span data-stu-id="c8c99-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="c8c99-128">Neste caso, o segundo parâmetro deve caber em 32 bits; se não, um erro de tempo de execução será levantado.</span><span class="sxs-lookup"><span data-stu-id="c8c99-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="c8c99-129">Tendo em conta duas expressões inteiros ou grandes inteiros, uma nova expressão inteiro ou grande inteiro pode ser formada usando os operadores `%` (modulo), `&&&` (bitwise And), `|||` (bitwise OR) ou `^^^` (bitwise XOR).</span><span class="sxs-lookup"><span data-stu-id="c8c99-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="c8c99-130">Dado um inteiro ou uma expressão inteiro à esquerda, e uma expressão inteiro à direita, os operadores `<<<` (turno da esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão esquerda.</span><span class="sxs-lookup"><span data-stu-id="c8c99-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="c8c99-131">O segundo parâmetro (o valor de deslocação) para uma das operações por turnos deve ser maior ou igual a zero; o comportamento para quantidades de mudança negativa é indefinido.</span><span class="sxs-lookup"><span data-stu-id="c8c99-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="c8c99-132">O montante de deslocação para qualquer uma das operações por turnos também deve caber em 32 bits; se não, um erro de tempo de execução será levantado.</span><span class="sxs-lookup"><span data-stu-id="c8c99-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="c8c99-133">Se o número a deslocar for um inteiro, então o valor do turno é interpretado `mod 64`; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="c8c99-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="c8c99-134">Tanto para valores inteiros como para grandes valores inteiros, as mudanças são aritméticas.</span><span class="sxs-lookup"><span data-stu-id="c8c99-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="c8c99-135">Mudar um valor negativo, quer à esquerda quer à direita, resultará num número negativo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="c8c99-136">Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c8c99-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="c8c99-137">Divisão integer e modulo inteiro seguem o C#mesmo comportamento para números negativos que .</span><span class="sxs-lookup"><span data-stu-id="c8c99-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="c8c99-138">Ou seja, `a % b` terá sempre o mesmo sinal que `a`, e `b * (a / b) + a % b` será sempre igual a `a`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="c8c99-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8c99-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="c8c99-140">5</span><span class="sxs-lookup"><span data-stu-id="c8c99-140">5</span></span> | <span data-ttu-id="c8c99-141">2</span><span class="sxs-lookup"><span data-stu-id="c8c99-141">2</span></span> | <span data-ttu-id="c8c99-142">2</span><span class="sxs-lookup"><span data-stu-id="c8c99-142">2</span></span> | <span data-ttu-id="c8c99-143">1</span><span class="sxs-lookup"><span data-stu-id="c8c99-143">1</span></span>
 <span data-ttu-id="c8c99-144">5</span><span class="sxs-lookup"><span data-stu-id="c8c99-144">5</span></span> | <span data-ttu-id="c8c99-145">-2</span><span class="sxs-lookup"><span data-stu-id="c8c99-145">-2</span></span> | <span data-ttu-id="c8c99-146">-2</span><span class="sxs-lookup"><span data-stu-id="c8c99-146">-2</span></span> | <span data-ttu-id="c8c99-147">1</span><span class="sxs-lookup"><span data-stu-id="c8c99-147">1</span></span>
 <span data-ttu-id="c8c99-148">-5</span><span class="sxs-lookup"><span data-stu-id="c8c99-148">-5</span></span> | <span data-ttu-id="c8c99-149">2</span><span class="sxs-lookup"><span data-stu-id="c8c99-149">2</span></span> | <span data-ttu-id="c8c99-150">-2</span><span class="sxs-lookup"><span data-stu-id="c8c99-150">-2</span></span> | <span data-ttu-id="c8c99-151">-1</span><span class="sxs-lookup"><span data-stu-id="c8c99-151">-1</span></span>
 <span data-ttu-id="c8c99-152">-5</span><span class="sxs-lookup"><span data-stu-id="c8c99-152">-5</span></span> | <span data-ttu-id="c8c99-153">-2</span><span class="sxs-lookup"><span data-stu-id="c8c99-153">-2</span></span> | <span data-ttu-id="c8c99-154">2</span><span class="sxs-lookup"><span data-stu-id="c8c99-154">2</span></span> | <span data-ttu-id="c8c99-155">-1</span><span class="sxs-lookup"><span data-stu-id="c8c99-155">-1</span></span>

<span data-ttu-id="c8c99-156">A grande divisão de inteiros e o modulo funcionam da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="c8c99-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="c8c99-157">Dada qualquer expressão numérica, pode ser formada uma nova expressão utilizando o operador `-` não-secundário.</span><span class="sxs-lookup"><span data-stu-id="c8c99-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="c8c99-158">A nova expressão será do mesmo tipo que a expressão constituinte.</span><span class="sxs-lookup"><span data-stu-id="c8c99-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="c8c99-159">Dada a expressão inteiro ou grande inteiro, pode formar-se uma nova expressão do mesmo tipo utilizando o operador `~~~` (complemento bitwise).</span><span class="sxs-lookup"><span data-stu-id="c8c99-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="c8c99-160">Expressões booleanas</span><span class="sxs-lookup"><span data-stu-id="c8c99-160">Boolean Expressions</span></span>

<span data-ttu-id="c8c99-161">Os dois valores `Bool` literários são `true` e `false`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="c8c99-162">Dadas duas expressões do mesmo tipo primitivo, os operadores `==` e `!=` binários podem ser utilizados para construir uma expressão `Bool`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="c8c99-163">A expressão será verdadeira se as duas expressões forem iguais, e falsas se não forem.</span><span class="sxs-lookup"><span data-stu-id="c8c99-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="c8c99-164">Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores não embrulhados podem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="c8c99-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="c8c99-165">Por exemplo, utilizando o operador "desembrulhar" `!` (explicado na página do [modelo do tipo Q#](xref:microsoft.quantum.language.type-model#user-defined-types)),</span><span class="sxs-lookup"><span data-stu-id="c8c99-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="c8c99-166">A comparação da igualdade entre valores `Qubit` é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.</span><span class="sxs-lookup"><span data-stu-id="c8c99-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="c8c99-167">O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.</span><span class="sxs-lookup"><span data-stu-id="c8c99-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="c8c99-168">A comparação da igualdade entre valores `Double` pode ser enganosa devido aos efeitos arredondamentos.</span><span class="sxs-lookup"><span data-stu-id="c8c99-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="c8c99-169">Por exemplo, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="c8c99-170">Tendo em conta duas expressões numéricas, os operadores binários `>`, `<`, `>=`e `<=` podem ser usados para construir uma nova expressão booleana que seja verdade se a primeira expressão for respectivamente maior do que, inferior ou igual, ou inferior ou igual à segunda expressão.</span><span class="sxs-lookup"><span data-stu-id="c8c99-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="c8c99-171">Dadas duas expressões booleanas, os operadores binários `and` e `or` podem ser usados para construir uma nova expressão booleana que é verdade se ambos (resp. ou ambos) as duas expressões forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="c8c99-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="c8c99-172">Dada qualquer expressão booleana, o `not` operador não-secundário pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.</span><span class="sxs-lookup"><span data-stu-id="c8c99-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="c8c99-173">Expressões de cordas</span><span class="sxs-lookup"><span data-stu-id="c8c99-173">String Expressions</span></span>

<span data-ttu-id="c8c99-174">Q# permite que as cordas sejam usadas na declaração `fail` e na função padrão `Log`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="c8c99-175">As cordas em Q# são literais ou cordas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="c8c99-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="c8c99-176">Os literais de cordas são semelhantes aos simples literais de cordas na maioria das línguas: uma sequência de caracteres Unicode fechados em citações duplas, `"`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="c8c99-177">Dentro de uma corda, o `\` de caracteres de corte traseiro pode ser usado para escapar a um personagem de citação dupla, e para inserir uma nova linha como `\n`, um retorno de carruagem como `\r`, e um separador como `\t`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="c8c99-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8c99-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="c8c99-179">A sintaxe Q# para interpolações de C# cordas é um subconjunto da sintaxe 7.0; Q# não suporta cordas interpoladas verbatim (multi-linhas).</span><span class="sxs-lookup"><span data-stu-id="c8c99-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="c8c99-180">Veja [*as Cordas Interpolated*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) para a C# sintaxe.</span><span class="sxs-lookup"><span data-stu-id="c8c99-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="c8c99-181">Expressões dentro de uma corda interpolada seguem C# Q# sintaxe, não sintaxe.</span><span class="sxs-lookup"><span data-stu-id="c8c99-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="c8c99-182">Qualquer expressão Q# válida pode aparecer numa corda interpolada.</span><span class="sxs-lookup"><span data-stu-id="c8c99-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="c8c99-183">Expressões Qubit</span><span class="sxs-lookup"><span data-stu-id="c8c99-183">Qubit Expressions</span></span>

<span data-ttu-id="c8c99-184">As únicas expressões `Qubit` são símbolos que estão ligados a `Qubit` valores ou elementos matrizes de `Qubit` matrizes.</span><span class="sxs-lookup"><span data-stu-id="c8c99-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="c8c99-185">Não há `Qubit` literal.</span><span class="sxs-lookup"><span data-stu-id="c8c99-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="c8c99-186">Expressões Pauli</span><span class="sxs-lookup"><span data-stu-id="c8c99-186">Pauli Expressions</span></span>

<span data-ttu-id="c8c99-187">Os quatro valores `Pauli`, `PauliI`, `PauliX`, `PauliY`e `PauliZ`, são todos expressões válidas `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="c8c99-188">Para além disso, as únicas expressões `Pauli` são símbolos que estão ligados a valores `Pauli` ou elementos matrizes de matrizes `Pauli`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="c8c99-189">Expressões de Resultados</span><span class="sxs-lookup"><span data-stu-id="c8c99-189">Result Expressions</span></span>

<span data-ttu-id="c8c99-190">Os dois valores `Result`, `One` e `Zero`, são expressões válidas `Result`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="c8c99-191">Para além disso, as únicas expressões `Result` são símbolos que estão ligados a valores `Result` ou elementos matrizes de matrizes `Result`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="c8c99-192">Note-se, em particular, que `One` não é o mesmo que o `1`inteiro , e não existe uma conversão direta entre eles.</span><span class="sxs-lookup"><span data-stu-id="c8c99-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="c8c99-193">O mesmo se aplica aos `Zero` e `0`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="c8c99-194">Expressões de alcance</span><span class="sxs-lookup"><span data-stu-id="c8c99-194">Range Expressions</span></span>

<span data-ttu-id="c8c99-195">Tendo em conta quaisquer três expressões `Int` `start`, `step`e `stop`, `start .. step .. stop` é uma expressão de alcance cujo primeiro elemento é `start`, o segundo elemento é `start+step`, o terceiro elemento é `start+step+step`, etc., até que `stop` seja passado.</span><span class="sxs-lookup"><span data-stu-id="c8c99-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="c8c99-196">Uma gama pode estar vazia se, por exemplo, `step` for positivo e `stop < start`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="c8c99-197">O último elemento da gama será `stop` se a diferença entre `start` e `stop` for um múltiplo integral de `step`; ou seja, a gama é inclusiva em ambas as extremidades.</span><span class="sxs-lookup"><span data-stu-id="c8c99-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="c8c99-198">Tendo em conta duas expressões `Int` `start` e `stop`, `start .. stop` é uma expressão de alcance igual a `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="c8c99-199">Note que o `step` implícito é +1 mesmo que `stop` seja inferior a `start`; em tal caso, o alcance está vazio.</span><span class="sxs-lookup"><span data-stu-id="c8c99-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="c8c99-200">Algumas gamas de exemplo são:</span><span class="sxs-lookup"><span data-stu-id="c8c99-200">Some example ranges are:</span></span>

- <span data-ttu-id="c8c99-201">`1..3` é o intervalo 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="c8c99-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="c8c99-202">`2..2..5` é o intervalo 2, 4.</span><span class="sxs-lookup"><span data-stu-id="c8c99-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="c8c99-203">`2..2..6` é o intervalo 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="c8c99-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="c8c99-204">`6..-2..2` é o intervalo 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="c8c99-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="c8c99-205">`2..1` é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="c8c99-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="c8c99-206">`2..6..7` é o intervalo 2.</span><span class="sxs-lookup"><span data-stu-id="c8c99-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="c8c99-207">`2..2..1` é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="c8c99-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="c8c99-208">`1..-1..2` é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="c8c99-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="c8c99-209">Expressões Insensíveis</span><span class="sxs-lookup"><span data-stu-id="c8c99-209">Callable Expressions</span></span>

<span data-ttu-id="c8c99-210">Um literal calivel é o nome de uma operação ou função definida no âmbito da compilação.</span><span class="sxs-lookup"><span data-stu-id="c8c99-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="c8c99-211">Por exemplo, `X` é uma operação literal que se refere à biblioteca padrão `X` operação, e `Message` é uma função literal que se refere à biblioteca padrão `Message` função.</span><span class="sxs-lookup"><span data-stu-id="c8c99-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="c8c99-212">Se uma operação suporta o functor `Adjoint`, então `Adjoint op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="c8c99-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="c8c99-213">Da mesma forma, se a operação suporta o functor `Controlled`, então `Controlled op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="c8c99-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="c8c99-214">Os tipos destas expressões são especificados em [Functors](xref:microsoft.quantum.language.type-model#functors).</span><span class="sxs-lookup"><span data-stu-id="c8c99-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="c8c99-215">Os functores (`Adjoint` e `Controlled`) ligam-se mais de perto do que todos os outros operadores, com exceção do `!` do operador desembrulhar e indexação de matriz com `[]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="c8c99-216">Assim, todos os seguintes são legais, assumindo que as operações apoiam os functors utilizados:</span><span class="sxs-lookup"><span data-stu-id="c8c99-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="c8c99-217">Um literal calivel pode ser usado como um valor, por exemplo, atribuir a uma variável ou passar para outra chamada.</span><span class="sxs-lookup"><span data-stu-id="c8c99-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="c8c99-218">Neste caso, se o callable tiver parâmetros de tipo, devem ser fornecidos como parte do valor calivel.</span><span class="sxs-lookup"><span data-stu-id="c8c99-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="c8c99-219">Um valor callable não pode ter nenhum tipo de parâmetros não especificados.</span><span class="sxs-lookup"><span data-stu-id="c8c99-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="c8c99-220">Por exemplo, se `Fun` for uma função com assinatura `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="c8c99-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="c8c99-221">Expressões de invocação callable</span><span class="sxs-lookup"><span data-stu-id="c8c99-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="c8c99-222">Dada uma expressão (operação ou função) insensível e uma expressão de tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada através da adesão da expressão de tuple à expressão calúgica.</span><span class="sxs-lookup"><span data-stu-id="c8c99-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="c8c99-223">O tipo de expressão de invocação é o tipo de saída da assinatura do callable.</span><span class="sxs-lookup"><span data-stu-id="c8c99-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="c8c99-224">Por exemplo, se `Op` for uma operação com `((Int, Qubit) => Double)`de assinatura, `Op(3, qubit1)` é uma expressão de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="c8c99-225">Da mesma forma, se `Sin` é uma função com `(Double -> Double)`de assinatura, `Sin(0.1)` é uma expressão de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="c8c99-226">Finalmente, se `Builder` é uma função com assinatura `(Int -> (Int -> Int))`, então `Builder(3)` é uma função de Into to Int.</span><span class="sxs-lookup"><span data-stu-id="c8c99-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="c8c99-227">Invocar o resultado de uma expressão de valor calivel requer um par extra de parênteses em torno da expressão caluniável.</span><span class="sxs-lookup"><span data-stu-id="c8c99-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="c8c99-228">Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:</span><span class="sxs-lookup"><span data-stu-id="c8c99-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="c8c99-229">Ao invocar uma chamada de tipo parametrizada, os parâmetros do tipo real podem ser especificados dentro dos suportes angulares `<` e `>` após a expressão caltável.</span><span class="sxs-lookup"><span data-stu-id="c8c99-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="c8c99-230">Isto é geralmente desnecessário, uma vez que o compilador Q# inferirá os tipos reais.</span><span class="sxs-lookup"><span data-stu-id="c8c99-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="c8c99-231">É necessário para aplicação parcial (ver abaixo) se um argumento de tipo parametrizado não for deixado não especificado.</span><span class="sxs-lookup"><span data-stu-id="c8c99-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="c8c99-232">Também é por vezes útil quando se passam operações com diferentes suportes de functor para um callable.</span><span class="sxs-lookup"><span data-stu-id="c8c99-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="c8c99-233">Por exemplo, se `Func` tiver `('T1, 'T2, 'T1) -> 'T2`de assinatura , `Op1` e `Op2` têm `(Qubit[] => Unit is Adj)`de assinatura , e `Op3` tem `(Qubit[] => Unit)`de assinatura , para invocar `Func` com `Op1` como primeiro argumento, `Op2` como o segundo, e `Op3` como o terceiro:</span><span class="sxs-lookup"><span data-stu-id="c8c99-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="c8c99-234">A especificação do tipo é necessária porque `Op3` e `Op1` têm tipos diferentes, por isso o compilador tratará isto como ambíguo sem a especificação.</span><span class="sxs-lookup"><span data-stu-id="c8c99-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="c8c99-235">Aplicação parcial</span><span class="sxs-lookup"><span data-stu-id="c8c99-235">Partial Application</span></span>

<span data-ttu-id="c8c99-236">Dada uma expressão calépável, um novo callable pode ser criado fornecendo um subconjunto dos argumentos ao callable.</span><span class="sxs-lookup"><span data-stu-id="c8c99-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="c8c99-237">Isto _chama-se aplicação parcial._</span><span class="sxs-lookup"><span data-stu-id="c8c99-237">This is called _partial application_.</span></span>

<span data-ttu-id="c8c99-238">Em Q#, um callable parcialmente aplicado é expresso escrevendo uma expressão de invocação normal, mas usando um sublinhado, `_`, para os argumentos não especificados.</span><span class="sxs-lookup"><span data-stu-id="c8c99-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="c8c99-239">O chamador resultante tem o mesmo tipo de resultado que a base callable, e as mesmas especializações para operações.</span><span class="sxs-lookup"><span data-stu-id="c8c99-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="c8c99-240">O tipo de entrada da aplicação parcial é simplesmente o tipo original com os argumentos especificados removidos.</span><span class="sxs-lookup"><span data-stu-id="c8c99-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="c8c99-241">Se uma variável mutável for aprovada como um argumento especificado ao criar uma aplicação parcial, o valor atual da variável é usado.</span><span class="sxs-lookup"><span data-stu-id="c8c99-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="c8c99-242">A alteração do valor da variável posteriormente não terá impacto na aplicação parcial.</span><span class="sxs-lookup"><span data-stu-id="c8c99-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="c8c99-243">Por exemplo, se `Op` tiver tipo `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span><span class="sxs-lookup"><span data-stu-id="c8c99-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="c8c99-244">`Op(5,(_,_))` tem `(((Qubit,Qubit), Double) => Unit is Adj)`tipo, assim como `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="c8c99-245">`Op(_,(_,1.0))` tem `((Int, (Qubit,Qubit)) => Unit is Adj)`tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="c8c99-246">`Op(_,((q1,q2),_))` tem `((Int,Double) => Unit is Adj)`tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="c8c99-247">Note que aplicamos equivalência de tuple singleton aqui.</span><span class="sxs-lookup"><span data-stu-id="c8c99-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="c8c99-248">Se o callable parcialmente aplicado tiver parâmetros de tipo que não podem ser inferidos pelo compilador, devem ser fornecidos no local de invocação.</span><span class="sxs-lookup"><span data-stu-id="c8c99-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="c8c99-249">A aplicação parcial não pode ter parâmetros de tipo não especificados.</span><span class="sxs-lookup"><span data-stu-id="c8c99-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="c8c99-250">Por exemplo, se `Op` tiver tipo `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span><span class="sxs-lookup"><span data-stu-id="c8c99-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="c8c99-251">Recursão</span><span class="sxs-lookup"><span data-stu-id="c8c99-251">Recursion</span></span>

<span data-ttu-id="c8c99-252">Q# os callables são permitidos ser direta ou indiretamente recursivos.</span><span class="sxs-lookup"><span data-stu-id="c8c99-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="c8c99-253">Ou seja, uma operação ou função pode chamar-se a si mesma, ou pode chamar outra chamada que, direta ou indiretamente, chama a operação de chamada.</span><span class="sxs-lookup"><span data-stu-id="c8c99-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="c8c99-254">No entanto, existem dois comentários importantes sobre a recura:</span><span class="sxs-lookup"><span data-stu-id="c8c99-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="c8c99-255">A utilização da recursição nas operações é suscetível de interferir com determinadas otimizações.</span><span class="sxs-lookup"><span data-stu-id="c8c99-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="c8c99-256">Isto pode ter um impacto substancial no tempo de execução do algoritmo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="c8c99-257">Ao executar um dispositivo quântico real, o espaço da pilha pode ser limitado, e assim a recursão profunda pode levar a um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="c8c99-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="c8c99-258">Em particular, o compilador Q# e o tempo de execução não identificam e otimizam a recursão da cauda.</span><span class="sxs-lookup"><span data-stu-id="c8c99-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="c8c99-259">Expressões tuple</span><span class="sxs-lookup"><span data-stu-id="c8c99-259">Tuple Expressions</span></span>

<span data-ttu-id="c8c99-260">Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas em `(` e `)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="c8c99-261">Por exemplo, `(1, One)` é uma expressão `(Int, Result)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="c8c99-262">Além dos literais, as únicas expressões de tuple são símbolos que estão ligados a valores de tuple, elementos marray de matrizes de tuple, e invocações calíveis que devolvem tuples.</span><span class="sxs-lookup"><span data-stu-id="c8c99-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="c8c99-263">Expressões de tipo definidas pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="c8c99-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="c8c99-264">Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="c8c99-265">Por exemplo, se `IntPair` é um tipo definido pelo utilizador com base em `(Int, Int)`, então `IntPair(2,3)` seria um literal válido desse tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="c8c99-266">Para além dos literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos manuais de matrizes desse tipo, e invocações calíveis que devolvem esse tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="c8c99-267">Desembrulhar Expressões</span><span class="sxs-lookup"><span data-stu-id="c8c99-267">Unwrap Expressions</span></span>

<span data-ttu-id="c8c99-268">Em Q#, o operador de desembrulhar é um ponto de exclamação `!`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="c8c99-269">Por exemplo, se `IntPair` é um tipo definido pelo utilizador com `(Int, Int)`de tipo subjacente, e `s` era uma variável com valor `IntPair(2,3)`, então `s!` seria `(2,3)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="c8c99-270">Para tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c8c99-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="c8c99-271">O operador de desembrulhar pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="c8c99-272">Assim, se `WrappedPair` é um tipo definido pelo utilizador com `IntPair`de tipo subjacente, e `t` é uma variável com valor `WrappedPair(IntPair(1,2))`, então `t!!` seria `(1,2)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="c8c99-273">O operador `!` tem uma precedência maior do que todos os outros operadores que não `[]` para indexação e corte de matriz.</span><span class="sxs-lookup"><span data-stu-id="c8c99-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="c8c99-274">`!` e `[]` ligar posicionalmente; ou seja, `a[i]![3]` deve ser lido como `((a[i])!)[3]`: tome o `i`'th elemento de `a`, desembrulhe-o, e, em seguida, obtenha o 3º elemento do valor desembrulhado (que deve ser uma matriz).</span><span class="sxs-lookup"><span data-stu-id="c8c99-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="c8c99-275">A precedência do operador `!` tem um impacto que pode não ser óbvio.</span><span class="sxs-lookup"><span data-stu-id="c8c99-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="c8c99-276">Se uma função ou operação devolver um valor que depois seja desembrulhado, a função ou chamada de operação deve ser encerrada em parênteses de modo a que o argumento se ligue à chamada e não ao desembrulhar.</span><span class="sxs-lookup"><span data-stu-id="c8c99-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="c8c99-277">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8c99-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="c8c99-278">Expressões de matriz</span><span class="sxs-lookup"><span data-stu-id="c8c99-278">Array Expressions</span></span>

<span data-ttu-id="c8c99-279">Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas em `[` e `]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="c8c99-280">Todos os elementos devem ser compatíveis com o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="c8c99-281">Se o tipo de elemento comum for um tipo de funcionamento ou de função, todos os elementos devem ter os mesmos tipos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="c8c99-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="c8c99-282">O tipo de elemento da matriz irá suportar todos os functors que sejam suportados por todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="c8c99-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="c8c99-283">Por exemplo, se `Op1`, `Op2`e `Op3` todos forem `Qubit[] => Unit`, mas `Op1` apoia `Adjoint`, `Op2` apoia `Controlled`, e `Op3` apoia ambos:</span><span class="sxs-lookup"><span data-stu-id="c8c99-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="c8c99-284">`[Op1, Op2]` é uma série de operações `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="c8c99-285">`[Op1, Op3]` é uma série de operações `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="c8c99-286">`[Op2, Op3]` é uma série de operações `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="c8c99-287">Não são permitidos os literais vazios, `[]`, não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c8c99-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="c8c99-288">Em vez disso, a utilização de `new ★[0]`, onde `★` é um espaço reservado para um tipo adequado, permite criar a matriz de comprimento zero desejada.</span><span class="sxs-lookup"><span data-stu-id="c8c99-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="c8c99-289">Tendo em conta duas matrizes do mesmo tipo, o operador de `+` binário pode ser usado para formar uma nova matriz que é a concatenação das duas matrizes.</span><span class="sxs-lookup"><span data-stu-id="c8c99-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="c8c99-290">Por exemplo, `[1,2,3] + [4,5,6]` é `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="c8c99-291">Criação de Matriz</span><span class="sxs-lookup"><span data-stu-id="c8c99-291">Array Creation</span></span>

<span data-ttu-id="c8c99-292">Dado um tipo e uma expressão `Int`, o operador `new` pode ser utilizado para alocar um novo conjunto do tamanho dado.</span><span class="sxs-lookup"><span data-stu-id="c8c99-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="c8c99-293">Por exemplo, `new Int[i+1]` atribuiria um novo conjunto de `Int` com elementos `i+1`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="c8c99-294">Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="c8c99-295">Na maioria dos casos, esta é uma variação de zero.</span><span class="sxs-lookup"><span data-stu-id="c8c99-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="c8c99-296">Para qubits e callables, que são referências a entidades, não existe um valor razoável por defeito.</span><span class="sxs-lookup"><span data-stu-id="c8c99-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="c8c99-297">Assim, para estes tipos, a predefinição é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="c8c99-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="c8c99-298">Isto é semelhante a uma referência C# nula em línguas como ou Java.</span><span class="sxs-lookup"><span data-stu-id="c8c99-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="c8c99-299">As matrizes que contenham qubits ou callables devem ser corretamente inicializadas com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança.</span><span class="sxs-lookup"><span data-stu-id="c8c99-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="c8c99-300">As rotinas de inicialização adequadas podem ser encontradas em <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="c8c99-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="c8c99-301">Os valores predefinidos para cada tipo são:</span><span class="sxs-lookup"><span data-stu-id="c8c99-301">The default values for each type are:</span></span>

<span data-ttu-id="c8c99-302">Tipo</span><span class="sxs-lookup"><span data-stu-id="c8c99-302">Type</span></span> | <span data-ttu-id="c8c99-303">Predefinição</span><span class="sxs-lookup"><span data-stu-id="c8c99-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="c8c99-304">_qubit inválido_</span><span class="sxs-lookup"><span data-stu-id="c8c99-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="c8c99-305">O alcance vazio, `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="c8c99-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="c8c99-306">_inválido callable_</span><span class="sxs-lookup"><span data-stu-id="c8c99-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="c8c99-307">Os tipos tuple são inicializados elemento a elemento.</span><span class="sxs-lookup"><span data-stu-id="c8c99-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="c8c99-308">Matrizes Irregulares</span><span class="sxs-lookup"><span data-stu-id="c8c99-308">Jagged Arrays</span></span>

<span data-ttu-id="c8c99-309">Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes.</span><span class="sxs-lookup"><span data-stu-id="c8c99-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="c8c99-310">Os elementos de uma matriz irregular podem ser de diferentes tamanhos.</span><span class="sxs-lookup"><span data-stu-id="c8c99-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="c8c99-311">O exemplo que se segue mostra como declarar e inicializar uma matriz irregular representando uma tabela de multiplicação.</span><span class="sxs-lookup"><span data-stu-id="c8c99-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="c8c99-312">Fatias de matriz</span><span class="sxs-lookup"><span data-stu-id="c8c99-312">Array Slices</span></span>

<span data-ttu-id="c8c99-313">Dada a expressão da matriz e uma expressão `Range`, pode formar-se uma nova expressão utilizando o operador de `[` e `]` fatiade matriz.</span><span class="sxs-lookup"><span data-stu-id="c8c99-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="c8c99-314">A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range`, na ordem definida pelo `Range`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="c8c99-315">Por exemplo, se `a` está ligada a uma série de `Double`s, então `a[3..-1..0]` é uma expressão `Double[]` que contém os primeiros quatro elementos de `a` mas na ordem inversa, como aparecem em `a`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="c8c99-316">Se o `Range` estiver vazio, então a fatia de matriz resultante será de zero comprimento.</span><span class="sxs-lookup"><span data-stu-id="c8c99-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="c8c99-317">Se a expressão da matriz não for um identificador simples, deve ser fechada a parênteses para cortar.</span><span class="sxs-lookup"><span data-stu-id="c8c99-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="c8c99-318">Por exemplo, se `a` e `b` forem ambos conjuntos de `Int`s, uma fatia da concatenação seria expressa como:</span><span class="sxs-lookup"><span data-stu-id="c8c99-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="c8c99-319">Todas as matrizes em Q# são baseadas em zero.</span><span class="sxs-lookup"><span data-stu-id="c8c99-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="c8c99-320">Ou seja, o primeiro elemento de uma matriz `a` é sempre `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="c8c99-321">A partir do nosso lançamento 0.8, apoiamos expressões contextuais para corte de alcance.</span><span class="sxs-lookup"><span data-stu-id="c8c99-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="c8c99-322">Em particular, os valores de início e fim de gama podem ser omitidos no contexto de uma expressão de corte de gama.</span><span class="sxs-lookup"><span data-stu-id="c8c99-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="c8c99-323">Nesse caso, o compilador aplicará as seguintes regras para inferir os delimitadores pretendidos para a gama.</span><span class="sxs-lookup"><span data-stu-id="c8c99-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="c8c99-324">Por exemplo, se o valor de início de gama for omitido, então o valor de início inferido</span><span class="sxs-lookup"><span data-stu-id="c8c99-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="c8c99-325">é zero se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="c8c99-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="c8c99-326">é o comprimento da matriz fatiada menos uma se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="c8c99-327">Se o valor final do intervalo for omitido, então o valor final inferido</span><span class="sxs-lookup"><span data-stu-id="c8c99-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="c8c99-328">é o comprimento da matriz fatiada menos um se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="c8c99-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="c8c99-329">é zero se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="c8c99-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="c8c99-330">Expressões do elemento matriz</span><span class="sxs-lookup"><span data-stu-id="c8c99-330">Array Element Expressions</span></span>

<span data-ttu-id="c8c99-331">Dada a expressão da matriz e uma expressão `Int`, pode ser formada uma nova expressão utilizando o operador de elementos de `[` e `]` matriz.</span><span class="sxs-lookup"><span data-stu-id="c8c99-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="c8c99-332">A nova expressão será do mesmo tipo que o tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="c8c99-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="c8c99-333">Por exemplo, se `a` está ligada a uma série de `Double`s, então `a[4]` é uma expressão `Double`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="c8c99-334">Se a expressão da matriz não for um identificador simples, deve ser fechada a sua parênteses para selecionar um elemento.</span><span class="sxs-lookup"><span data-stu-id="c8c99-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="c8c99-335">Por exemplo, se `a` e `b` forem ambos conjuntos de `Int`s, um elemento da constcatenação seria expresso como:</span><span class="sxs-lookup"><span data-stu-id="c8c99-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="c8c99-336">Todas as matrizes em Q# são baseadas em zero.</span><span class="sxs-lookup"><span data-stu-id="c8c99-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="c8c99-337">Ou seja, o primeiro elemento de uma matriz `a` é sempre `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="c8c99-338">Expressões de cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="c8c99-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="c8c99-339">Novas matrizes podem ser criadas a partir das existentes através de expressões de cópia e atualização.</span><span class="sxs-lookup"><span data-stu-id="c8c99-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="c8c99-340">Uma expressão de cópia e atualização é uma expressão do formulário `expression1 w/ expression2 <- expression3`, onde `expression1` tem de ser de tipo `T[]` para algum tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="c8c99-341">A segunda `expression2` define os índices dos elementos a modificar em comparação com a matriz em `expression1` e tem de ser de tipo `Int` ou de `Range`tipo .</span><span class="sxs-lookup"><span data-stu-id="c8c99-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="c8c99-342">Se `expression2` for de tipo `Int`, `expression3` tem de ser do tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="c8c99-343">Se `expression2` for de tipo `Range`, `expression3` tem de ser do tipo `T[]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="c8c99-344">Uma expressão de cópia e atualização `arr w/ idx <- value` constrói um novo conjunto com todos os elementos definidos para o elemento correspondente em `arr`, com exceção dos elementos `idx`, que estão definidos para os ou os `value`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="c8c99-345">Por exemplo, se `arr` contém uma matriz `[0,1,2,3]`, então</span><span class="sxs-lookup"><span data-stu-id="c8c99-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="c8c99-346">`arr w/ 0 <- 10` é a matriz `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="c8c99-347">`arr w/ 2 <- 10` é a matriz `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="c8c99-348">`arr w/ 0..2..3 <- [10,12]` é a matriz `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="c8c99-349">Existem expressões semelhantes para itens nomeados em tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c8c99-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="c8c99-350">Considere, por exemplo, o tipo</span><span class="sxs-lookup"><span data-stu-id="c8c99-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="c8c99-351">Se `c` contém o valor do tipo `Complex(1.,-1.)`, então `c w/ Re <- 0.` é uma expressão de tipo `Complex` que avalia para `Complex(0.,-1.)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="c8c99-352">Expressões Condicionais</span><span class="sxs-lookup"><span data-stu-id="c8c99-352">Conditional Expressions</span></span>

<span data-ttu-id="c8c99-353">Tendo em conta duas outras expressões do mesmo tipo e uma expressão booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação `?` e a barra vertical `|`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="c8c99-354">Por exemplo, `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="c8c99-355">Neste exemplo, o valor da expressão condicional será `c` se `a==b` for verdade e `d` se for falsa.</span><span class="sxs-lookup"><span data-stu-id="c8c99-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="c8c99-356">As duas expressões podem avaliar para operações que tenham as mesmas inputs e saídas, mas suportam diferentes functores.</span><span class="sxs-lookup"><span data-stu-id="c8c99-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="c8c99-357">Neste caso, o tipo de expressão condicional é uma operação com as inputs e saídas que suporta todos os functors suportados por ambas as expressões.</span><span class="sxs-lookup"><span data-stu-id="c8c99-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="c8c99-358">Por exemplo, se `Op1`, `Op2`e `Op3` todos forem `Qubit[]=>Unit`, mas `Op1` apoia `Adjoint`, `Op2` apoia `Controlled`, e `Op3` apoia ambos:</span><span class="sxs-lookup"><span data-stu-id="c8c99-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="c8c99-359">`flag ? Op1 | Op2` é uma operação `(Qubit[] => Unit)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="c8c99-360">`flag ? Op1 | Op3` é uma operação `(Qubit[] => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="c8c99-361">`flag ? Op2 | Op3` é uma operação `(Qubit[] => Unit is Ctl)`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="c8c99-362">Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de operação, essa chamada só ocorrerá se esse resultado for o valor da chamada.</span><span class="sxs-lookup"><span data-stu-id="c8c99-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="c8c99-363">Por exemplo, no caso `a==b ? C(qs) | D(qs)`, se `a==b` for verdade, então a operação `C` será invocada, e se for falsa, então apenas `D` serão invocadas.</span><span class="sxs-lookup"><span data-stu-id="c8c99-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="c8c99-364">Isto é semelhante ao curto-circuito noutras línguas.</span><span class="sxs-lookup"><span data-stu-id="c8c99-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="c8c99-365">Precedência do operador</span><span class="sxs-lookup"><span data-stu-id="c8c99-365">Operator Precedence</span></span>

<span data-ttu-id="c8c99-366">Todos os operadores binários são associativos de direito, com exceção `^`.</span><span class="sxs-lookup"><span data-stu-id="c8c99-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="c8c99-367">Os suportes, `[` e `]`, para corte e indexação de matrizes, ligam-se perante qualquer operador.</span><span class="sxs-lookup"><span data-stu-id="c8c99-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="c8c99-368">Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.</span><span class="sxs-lookup"><span data-stu-id="c8c99-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="c8c99-369">Os parênteses para a exploração e a invocação de funções também se ligam perante qualquer operador, mas após a indexação da matriz e functores.</span><span class="sxs-lookup"><span data-stu-id="c8c99-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="c8c99-370">Operadores por ordem de precedência, dos mais elevados aos mais baixos:</span><span class="sxs-lookup"><span data-stu-id="c8c99-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="c8c99-371">Operador</span><span class="sxs-lookup"><span data-stu-id="c8c99-371">Operator</span></span> | <span data-ttu-id="c8c99-372">Rio Arity</span><span class="sxs-lookup"><span data-stu-id="c8c99-372">Arity</span></span> | <span data-ttu-id="c8c99-373">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8c99-373">Description</span></span> | <span data-ttu-id="c8c99-374">Tipos de operand</span><span class="sxs-lookup"><span data-stu-id="c8c99-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="c8c99-375">`!` de rasto</span><span class="sxs-lookup"><span data-stu-id="c8c99-375">trailing `!`</span></span> | <span data-ttu-id="c8c99-376">Unary</span><span class="sxs-lookup"><span data-stu-id="c8c99-376">Unary</span></span> | <span data-ttu-id="c8c99-377">Desembrulhar</span><span class="sxs-lookup"><span data-stu-id="c8c99-377">Unwrap</span></span> | <span data-ttu-id="c8c99-378">Qualquer tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="c8c99-378">Any user-defined type</span></span>
 <span data-ttu-id="c8c99-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="c8c99-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="c8c99-380">Unary</span><span class="sxs-lookup"><span data-stu-id="c8c99-380">Unary</span></span> | <span data-ttu-id="c8c99-381">Negativa numérica, um complemento bitwise, negação lógica</span><span class="sxs-lookup"><span data-stu-id="c8c99-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="c8c99-382">`Int`, `BigInt` ou `Double` para `-`, `Int` ou `BigInt` para `~~~`, `Bool` para `not`</span><span class="sxs-lookup"><span data-stu-id="c8c99-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="c8c99-383">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-383">Binary</span></span> | <span data-ttu-id="c8c99-384">Poder inteiro</span><span class="sxs-lookup"><span data-stu-id="c8c99-384">Integer power</span></span> | <span data-ttu-id="c8c99-385">`Int` ou `BigInt` para a base, `Int` para o expoente</span><span class="sxs-lookup"><span data-stu-id="c8c99-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="c8c99-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="c8c99-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="c8c99-387">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-387">Binary</span></span> | <span data-ttu-id="c8c99-388">Divisão, multiplicação, modulo inteiro</span><span class="sxs-lookup"><span data-stu-id="c8c99-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="c8c99-389">`Int`, `BigInt` ou `Double` para `/` e `*`, `Int` ou `BigInt` para `%`</span><span class="sxs-lookup"><span data-stu-id="c8c99-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="c8c99-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="c8c99-390">`+`, `-`</span></span> | <span data-ttu-id="c8c99-391">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-391">Binary</span></span> | <span data-ttu-id="c8c99-392">Adição ou cadeia e concatenação de cordas, subtração</span><span class="sxs-lookup"><span data-stu-id="c8c99-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="c8c99-393">`Int`, `BigInt` ou `Double`, adicionalmente `String` ou qualquer tipo de matriz para `+`</span><span class="sxs-lookup"><span data-stu-id="c8c99-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="c8c99-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="c8c99-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="c8c99-395">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-395">Binary</span></span> | <span data-ttu-id="c8c99-396">Turno da esquerda, turno da direita</span><span class="sxs-lookup"><span data-stu-id="c8c99-396">Left shift, right shift</span></span> | <span data-ttu-id="c8c99-397">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c8c99-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="c8c99-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="c8c99-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="c8c99-399">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-399">Binary</span></span> | <span data-ttu-id="c8c99-400">Comparações menos ou iguais, mais do que iguais, maiores do que iguais ou iguais</span><span class="sxs-lookup"><span data-stu-id="c8c99-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="c8c99-401">`Int`, `BigInt` ou `Double`</span><span class="sxs-lookup"><span data-stu-id="c8c99-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="c8c99-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="c8c99-402">`==`, `!=`</span></span> | <span data-ttu-id="c8c99-403">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-403">Binary</span></span> | <span data-ttu-id="c8c99-404">comparações iguais e não iguais</span><span class="sxs-lookup"><span data-stu-id="c8c99-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="c8c99-405">qualquer tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="c8c99-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="c8c99-406">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-406">Binary</span></span> | <span data-ttu-id="c8c99-407">Bitwise E</span><span class="sxs-lookup"><span data-stu-id="c8c99-407">Bitwise AND</span></span> | <span data-ttu-id="c8c99-408">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c8c99-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="c8c99-409">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-409">Binary</span></span> | <span data-ttu-id="c8c99-410">Bitwise XOR</span><span class="sxs-lookup"><span data-stu-id="c8c99-410">Bitwise XOR</span></span> | <span data-ttu-id="c8c99-411">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c8c99-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="c8c99-412">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-412">Binary</span></span> | <span data-ttu-id="c8c99-413">Bitwise OU</span><span class="sxs-lookup"><span data-stu-id="c8c99-413">Bitwise OR</span></span> | <span data-ttu-id="c8c99-414">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c8c99-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="c8c99-415">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-415">Binary</span></span> | <span data-ttu-id="c8c99-416">Lógico E</span><span class="sxs-lookup"><span data-stu-id="c8c99-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="c8c99-417">Binário</span><span class="sxs-lookup"><span data-stu-id="c8c99-417">Binary</span></span> | <span data-ttu-id="c8c99-418">Lógica OU</span><span class="sxs-lookup"><span data-stu-id="c8c99-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="c8c99-419">Binário/Ternary</span><span class="sxs-lookup"><span data-stu-id="c8c99-419">Binary/Ternary</span></span> | <span data-ttu-id="c8c99-420">Operador de gama</span><span class="sxs-lookup"><span data-stu-id="c8c99-420">Range operator</span></span> | `Int`
 <span data-ttu-id="c8c99-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="c8c99-421">`?` `|`</span></span> | <span data-ttu-id="c8c99-422">Ternário</span><span class="sxs-lookup"><span data-stu-id="c8c99-422">Ternary</span></span> | <span data-ttu-id="c8c99-423">Condicional</span><span class="sxs-lookup"><span data-stu-id="c8c99-423">Conditional</span></span> | <span data-ttu-id="c8c99-424">`Bool` para o lado esquerdo</span><span class="sxs-lookup"><span data-stu-id="c8c99-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="c8c99-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="c8c99-425">`w/` `<-`</span></span> | <span data-ttu-id="c8c99-426">Ternário</span><span class="sxs-lookup"><span data-stu-id="c8c99-426">Ternary</span></span> | <span data-ttu-id="c8c99-427">Cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="c8c99-427">Copy-and-update</span></span> | <span data-ttu-id="c8c99-428">ver [expressões de cópia e atualização](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="c8c99-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
