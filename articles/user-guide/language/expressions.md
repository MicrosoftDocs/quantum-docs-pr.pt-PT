---
title: 'Expressãos tipo em Q #'
description: Entenda como especificar, referenciar e combinar constantes, variáveis, operadores, operações e funções como expressões em Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 1821df6a3a51a62b44f3ccd96b127577c5db990a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415393"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="1b88b-103">Expressãos tipo em Q #</span><span class="sxs-lookup"><span data-stu-id="1b88b-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="1b88b-104">Expressões numéricas</span><span class="sxs-lookup"><span data-stu-id="1b88b-104">Numeric Expressions</span></span>

<span data-ttu-id="1b88b-105">Expressões numéricas são expressões do `Int` `BigInt` tipo, ou `Double` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="1b88b-106">Ou seja, ou são números inteiros ou de pontos flutuantes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="1b88b-107">`Int`literais em Q# são escritos como uma sequência de dígitos.</span><span class="sxs-lookup"><span data-stu-id="1b88b-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="1b88b-108">Os inteiros hexadecimais e binários são suportados e escritos com um `0x` `0b` prefixo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1b88b-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="1b88b-109">`BigInt`literais em Q# têm um rasto `l` ou `L` sufixo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="1b88b-110">Os grandes inteiros hexadecimais são suportados e escritos com um prefixo "0x".</span><span class="sxs-lookup"><span data-stu-id="1b88b-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="1b88b-111">Assim, todas são utilizações válidas de `BigInt` literais:</span><span class="sxs-lookup"><span data-stu-id="1b88b-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="1b88b-112">`Double`literais em Q# são números de ponto flutuante escritos usando dígitos decimais.</span><span class="sxs-lookup"><span data-stu-id="1b88b-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="1b88b-113">Podem ser escritos com ou sem ponto decimal, `.` ou uma parte exponencial indicada com 'e' ou 'E' (após o qual apenas são válidos um possível sinal negativo e dígitos decimais).</span><span class="sxs-lookup"><span data-stu-id="1b88b-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="1b88b-114">Seguem-se `Double` literais válidos: `0.0` . . . `1.2e5` `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="1b88b-115">Dada a expressão de matriz de qualquer tipo de elemento, pode formar uma `Int` expressão utilizando a [`Length`](xref:microsoft.quantum.core.length) função incorporada, com a expressão de matriz fechada em parênteses.</span><span class="sxs-lookup"><span data-stu-id="1b88b-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="1b88b-116">Por exemplo, se `a` estiver ligado a uma matriz, então é uma expressão `Length(a)` inteiro.</span><span class="sxs-lookup"><span data-stu-id="1b88b-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="1b88b-117">Se `b` for uma matriz de inteiros, `Int[][]` então é o número de `Length(b)` sub-matrizes em `b` , e é o número de `Length(b[1])` inteiros na segunda sub-matriz em `b` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="1b88b-118">Tendo em conta duas expressões numéricas do mesmo tipo, os operadores `+` `-` `*` binários, e `/` podem ser usados para formar uma nova expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="1b88b-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="1b88b-119">O tipo de nova expressão é o mesmo que os tipos de expressões constituintes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="1b88b-120">Tendo em conta duas expressões mais recentes, utilize o operador binário `^` (potência) para formar uma nova expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="1b88b-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="1b88b-121">Da mesma forma, você também pode usar `^` com duas expressões duplas para formar uma nova expressão dupla.</span><span class="sxs-lookup"><span data-stu-id="1b88b-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="1b88b-122">Finalmente, você pode usar `^` com um grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão de inteiro.</span><span class="sxs-lookup"><span data-stu-id="1b88b-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="1b88b-123">Neste caso, o segundo parâmetro deve encaixar em 32 bits; caso contrário, levanta um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1b88b-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="1b88b-124">Tendo em conta duas expressões inteiros ou grandes, formam uma nova expressão inteiro ou grande, utilizando os `%` operadores (modulus), `&&&` (bitwise E), `|||` (bitwise OR) ou `^^^` (bitwise XOR).</span><span class="sxs-lookup"><span data-stu-id="1b88b-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="1b88b-125">Dada a expressão de um inteiro ou de um grande inteiro à esquerda, e uma expressão inteiro à direita, use os `<<<` operadores (mudança aritmética à esquerda) ou `>>>` (mudança de direita aritmética) para criar uma nova expressão com o mesmo tipo que a expressão da esquerda.</span><span class="sxs-lookup"><span data-stu-id="1b88b-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="1b88b-126">O segundo parâmetro (a quantidade de turno) para uma operação por turnos deve ser superior ou igual a zero; o comportamento para quantidades de turno negativas é indefinido.</span><span class="sxs-lookup"><span data-stu-id="1b88b-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="1b88b-127">O valor de deslocação para qualquer operação por turnos também deve caber em 32 bits; caso contrário, levanta um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1b88b-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="1b88b-128">Se o número alterado for um número inteiro, então o valor do turno é `mod 64` interpretado; isto é, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="1b88b-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="1b88b-129">Tanto para os valores inteiros como para os grandes valores inteiros, as mudanças são aritmética.</span><span class="sxs-lookup"><span data-stu-id="1b88b-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="1b88b-130">Deslocar um valor negativo, tanto à esquerda como à direita, resulta num número negativo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="1b88b-131">Ou seja, deslocar um passo para a esquerda ou para a direita é o mesmo que multiplicar ou dividir por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1b88b-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="1b88b-132">A divisão de inteiros e o módulo inteiro seguem o mesmo comportamento para números negativos como C#.</span><span class="sxs-lookup"><span data-stu-id="1b88b-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="1b88b-133">Ou seja, `a % b` tem sempre o mesmo sinal que , e sempre `a` `b * (a / b) + a % b` `a` igual.</span><span class="sxs-lookup"><span data-stu-id="1b88b-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span>
<span data-ttu-id="1b88b-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b88b-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="1b88b-135">5</span><span class="sxs-lookup"><span data-stu-id="1b88b-135">5</span></span> | <span data-ttu-id="1b88b-136">2</span><span class="sxs-lookup"><span data-stu-id="1b88b-136">2</span></span> | <span data-ttu-id="1b88b-137">2</span><span class="sxs-lookup"><span data-stu-id="1b88b-137">2</span></span> | <span data-ttu-id="1b88b-138">1</span><span class="sxs-lookup"><span data-stu-id="1b88b-138">1</span></span>
 <span data-ttu-id="1b88b-139">5</span><span class="sxs-lookup"><span data-stu-id="1b88b-139">5</span></span> | <span data-ttu-id="1b88b-140">-2</span><span class="sxs-lookup"><span data-stu-id="1b88b-140">-2</span></span> | <span data-ttu-id="1b88b-141">-2</span><span class="sxs-lookup"><span data-stu-id="1b88b-141">-2</span></span> | <span data-ttu-id="1b88b-142">1</span><span class="sxs-lookup"><span data-stu-id="1b88b-142">1</span></span>
 <span data-ttu-id="1b88b-143">-5</span><span class="sxs-lookup"><span data-stu-id="1b88b-143">-5</span></span> | <span data-ttu-id="1b88b-144">2</span><span class="sxs-lookup"><span data-stu-id="1b88b-144">2</span></span> | <span data-ttu-id="1b88b-145">-2</span><span class="sxs-lookup"><span data-stu-id="1b88b-145">-2</span></span> | <span data-ttu-id="1b88b-146">-1</span><span class="sxs-lookup"><span data-stu-id="1b88b-146">-1</span></span>
 <span data-ttu-id="1b88b-147">-5</span><span class="sxs-lookup"><span data-stu-id="1b88b-147">-5</span></span> | <span data-ttu-id="1b88b-148">-2</span><span class="sxs-lookup"><span data-stu-id="1b88b-148">-2</span></span> | <span data-ttu-id="1b88b-149">2</span><span class="sxs-lookup"><span data-stu-id="1b88b-149">2</span></span> | <span data-ttu-id="1b88b-150">-1</span><span class="sxs-lookup"><span data-stu-id="1b88b-150">-1</span></span>

<span data-ttu-id="1b88b-151">A grande divisão de inteiros e as operações de módulos funcionam da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="1b88b-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="1b88b-152">Dada qualquer expressão numérica, pode formar uma nova expressão usando o `-` operador unary.</span><span class="sxs-lookup"><span data-stu-id="1b88b-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="1b88b-153">A nova expressão é do mesmo tipo que a expressão constituinte.</span><span class="sxs-lookup"><span data-stu-id="1b88b-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="1b88b-154">Dada qualquer expressão inteiro ou grande, pode formar uma nova expressão do mesmo tipo utilizando o `~~~` operador (pequeno complemento) unary.</span><span class="sxs-lookup"><span data-stu-id="1b88b-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="1b88b-155">Expressões booleanas</span><span class="sxs-lookup"><span data-stu-id="1b88b-155">Boolean Expressions</span></span>

<span data-ttu-id="1b88b-156">Os dois `Bool` valores literais são `true` `false` e.</span><span class="sxs-lookup"><span data-stu-id="1b88b-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="1b88b-157">Tendo em conta duas expressões do mesmo tipo primitivo, os `==` `!=` operadores binários podem ser utilizados para construir uma `Bool` expressão.</span><span class="sxs-lookup"><span data-stu-id="1b88b-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="1b88b-158">A expressão é verdadeira se as duas expressões forem iguais e falsas se não.</span><span class="sxs-lookup"><span data-stu-id="1b88b-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="1b88b-159">Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores desembrulhados podem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="1b88b-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="1b88b-160">Por exemplo, utilizando o operador "desembrulhar" `!` (explicado em pormenor nos [tipos em Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="1b88b-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="1b88b-161">A comparação entre igualdade de `Qubit` valores é a igualdade de identidade; isto é, se as duas expressões identificam o mesmo qubit.</span><span class="sxs-lookup"><span data-stu-id="1b88b-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="1b88b-162">Os estados dos dois qubits não são comparados, acedidos, medidos ou modificados por esta comparação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="1b88b-163">A comparação entre a igualdade e `Double` os valores pode ser enganosa devido aos efeitos de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="1b88b-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="1b88b-164">Por exemplo, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="1b88b-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="1b88b-165">Tendo em conta duas expressões numéricas, os operadores binários `>` , e podem ser `<` `>=` `<=` usados para construir uma nova expressão booleana que é verdade se a primeira expressão for respectivamente maior do que, menos do que, maior ou igual a, ou inferior ou igual à segunda expressão.</span><span class="sxs-lookup"><span data-stu-id="1b88b-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="1b88b-166">Dadas as duas expressões booleanas, use o `and` operador binário para construir uma nova expressão booleana que é verdade se ambas as expressões forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="1b88b-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="1b88b-167">Da mesma forma, a utilização do `or` operador cria uma expressão que é verdadeira se uma das duas expressões for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="1b88b-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="1b88b-168">Dada qualquer expressão booleana, o `not` operador unary pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.</span><span class="sxs-lookup"><span data-stu-id="1b88b-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="1b88b-169">Expressões de cadeia</span><span class="sxs-lookup"><span data-stu-id="1b88b-169">String expressions</span></span>

<span data-ttu-id="1b88b-170">Q# permite que as cordas sejam utilizadas na `fail` declaração (explicada no [Fluxo de Controlo)](xref:microsoft.quantum.guide.controlflow#fail-statement)e na [`Message`](xref:microsoft.quantum.intrinsic.message) função padrão.</span><span class="sxs-lookup"><span data-stu-id="1b88b-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="1b88b-171">O comportamento específico deste último depende do simulador utilizado, mas normalmente escreve uma mensagem para a consola anfitriã quando é chamado durante um programa Q#.</span><span class="sxs-lookup"><span data-stu-id="1b88b-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="1b88b-172">As cordas em Q# são literais ou cordas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="1b88b-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="1b88b-173">As letras de corda são semelhantes às simples cordas literais na maioria das línguas: uma sequência de caracteres Unicode incluídos em citações duplas `" "` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="1b88b-174">Dentro de uma corda, use o personagem de backslash `\` para escapar a um personagem de dupla citação `\"` (), ou para inserir uma nova linha ( ), um retorno de `\n` transporte ( ) ou um `\r` separador ( ). `\t`</span><span class="sxs-lookup"><span data-stu-id="1b88b-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="1b88b-175">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b88b-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="1b88b-176">Cordas interpoladas</span><span class="sxs-lookup"><span data-stu-id="1b88b-176">Interpolated strings</span></span>

<span data-ttu-id="1b88b-177">A sintaxe Q# para interpolações de cordas é um subconjunto da sintaxe C#.</span><span class="sxs-lookup"><span data-stu-id="1b88b-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="1b88b-178">Seguem-se os pontos-chave que dizem respeito a Q#:</span><span class="sxs-lookup"><span data-stu-id="1b88b-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="1b88b-179">Para identificar uma corda literal como uma corda interpolada, prepare-a com o `$` símbolo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="1b88b-180">Não pode haver espaço branco entre o `$` e o que começa uma corda `"` literal.</span><span class="sxs-lookup"><span data-stu-id="1b88b-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="1b88b-181">O seguinte é um exemplo básico usando a [`Message`](xref:microsoft.quantum.intrinsic.message) função para escrever o resultado de uma medição para a consola, ao lado de outras expressões Q#.</span><span class="sxs-lookup"><span data-stu-id="1b88b-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="1b88b-182">Qualquer expressão Q# válida pode aparecer numa corda interpolada.</span><span class="sxs-lookup"><span data-stu-id="1b88b-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="1b88b-183">Expressões dentro de uma corda interpolada seguem a sintaxe Q#, não a sintaxe C#.</span><span class="sxs-lookup"><span data-stu-id="1b88b-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="1b88b-184">A distinção mais notável é que Q# não suporta cordas interpoladas verbatim (multi-line).</span><span class="sxs-lookup"><span data-stu-id="1b88b-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="1b88b-185">Para obter mais detalhes sobre a sintaxe C#, consulte [*As Cordas Interpoladas*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="1b88b-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="1b88b-186">Expressões de alcance</span><span class="sxs-lookup"><span data-stu-id="1b88b-186">Range Expressions</span></span>

<span data-ttu-id="1b88b-187">Tendo em conta as três `Int` expressões `start` , e , a expressão é uma expressão de alcance cujo primeiro elemento é , o `step` segundo elemento é , o terceiro elemento é `stop` , e assim `start .. step .. stop` `start` `start+step` por `start+step+step` diante, até `stop` passar.</span><span class="sxs-lookup"><span data-stu-id="1b88b-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="1b88b-188">Uma gama pode estar vazia se, por exemplo, `step` for positiva e . `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="1b88b-189">O alcance é inclusivo em ambas as extremidades.</span><span class="sxs-lookup"><span data-stu-id="1b88b-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="1b88b-190">Ou seja, se a diferença entre `start` e é um conjunto inteiro `stop` `step` de, o último elemento da gama será `stop` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="1b88b-191">Tendo em conta `Int` duas expressões `start` `stop` e, a expressão `start .. stop` é uma expressão de alcance que é igual a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="1b88b-192">Note que o implícito `step` é +1 mesmo que `stop` seja `start` inferior; em tal caso, o intervalo está vazio.</span><span class="sxs-lookup"><span data-stu-id="1b88b-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="1b88b-193">Algumas gamas de exemplos são:</span><span class="sxs-lookup"><span data-stu-id="1b88b-193">Some example ranges are:</span></span>

- <span data-ttu-id="1b88b-194">`1..3`é o alcance 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="1b88b-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="1b88b-195">`2..2..5`é o alcance 2, 4.</span><span class="sxs-lookup"><span data-stu-id="1b88b-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="1b88b-196">`2..2..6`é o alcance 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="1b88b-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="1b88b-197">`6..-2..2`é o alcance 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="1b88b-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="1b88b-198">`2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="1b88b-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="1b88b-199">`2..6..7`é o alcance 2.</span><span class="sxs-lookup"><span data-stu-id="1b88b-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="1b88b-200">`2..2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="1b88b-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="1b88b-201">`1..-1..2`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="1b88b-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="1b88b-202">Expressões qubit</span><span class="sxs-lookup"><span data-stu-id="1b88b-202">Qubit Expressions</span></span>

<span data-ttu-id="1b88b-203">As `Qubit` únicas expressões são símbolos que estão ligados a `Qubit` valores ou elementos de `Qubit` matrizes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="1b88b-204">Não há `Qubit` literais.</span><span class="sxs-lookup"><span data-stu-id="1b88b-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="1b88b-205">Expressões Pauli</span><span class="sxs-lookup"><span data-stu-id="1b88b-205">Pauli Expressions</span></span>

<span data-ttu-id="1b88b-206">Os quatro `Pauli` valores são `PauliI` `PauliX` `PauliY` `PauliZ` `Pauli` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="1b88b-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="1b88b-207">Para além disso, as `Pauli` únicas expressões são símbolos que estão ligados a `Pauli` valores ou elementos de `Pauli` matrizes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="1b88b-208">Expressões de resultados</span><span class="sxs-lookup"><span data-stu-id="1b88b-208">Result Expressions</span></span>

<span data-ttu-id="1b88b-209">Os dois `Result` `One` valores, `Zero` e, são `Result` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="1b88b-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="1b88b-210">Para além disso, as `Result` únicas expressões são símbolos que estão ligados a `Result` valores ou elementos de `Result` matrizes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="1b88b-211">Em particular, note que não é o mesmo que `One` o inteiro , e não há conversão direta entre `1` eles.</span><span class="sxs-lookup"><span data-stu-id="1b88b-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="1b88b-212">O mesmo se aplica `Zero` `0` e. .</span><span class="sxs-lookup"><span data-stu-id="1b88b-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="1b88b-213">Expressões tuple</span><span class="sxs-lookup"><span data-stu-id="1b88b-213">Tuple Expressions</span></span>

<span data-ttu-id="1b88b-214">Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas em parênteses.</span><span class="sxs-lookup"><span data-stu-id="1b88b-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="1b88b-215">Por exemplo, `(1, One)` é uma `(Int, Result)` expressão.</span><span class="sxs-lookup"><span data-stu-id="1b88b-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="1b88b-216">Além das literais, as únicas expressões de tuple são símbolos que são obrigados a tuple valores, elementos de matrizes de tuple, e invocações callable que devolvem tuples.</span><span class="sxs-lookup"><span data-stu-id="1b88b-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="1b88b-217">Expressões de tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="1b88b-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="1b88b-218">Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="1b88b-219">Por exemplo, se `IntPair` for um tipo definido pelo utilizador baseado em , `(Int, Int)` então é um literal válido desse `IntPair(2, 3)` tipo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="1b88b-220">Além das literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos de matrizes desse tipo, e invocações pôveis que devolvem esse tipo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="1b88b-221">Desembrulhar expressões</span><span class="sxs-lookup"><span data-stu-id="1b88b-221">Unwrap Expressions</span></span>

<span data-ttu-id="1b88b-222">Em Q#, o operador de desembrulhar é um ponto de exclamação em fuga `!` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="1b88b-223">Por exemplo, se `IntPair` for um tipo definido pelo utilizador com o tipo subjacente e é uma `(Int, Int)` `s` variável com `IntPair(2, 3)` valor, então `s!` é `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="1b88b-224">Para os tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador, pode repetir o operador de desembrulhá-lo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="1b88b-225">Por exemplo, `s!!` indica o valor duplamente desembrulhado de `s` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="1b88b-226">Assim, se `WrappedPair` for um tipo definido pelo utilizador com tipo `IntPair` subjacente, e é uma `t` variável com `WrappedPair(IntPair(1,2))` valor, então `t!!` é `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="1b88b-227">O `!` operador tem uma precedência mais elevada do que todos os outros operadores que não para a `[]` indexação e corte de matrizes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="1b88b-228">`!`e `[]` ligar posicionalmente; ou seja, `a[i]![3]` lê-se como `((a[i])!)[3]` : pegue no elemento de , `i` `a` desembrulhe-o e, em seguida, obtenha o terceiro elemento do valor desembrulhado (que deve ser uma matriz).</span><span class="sxs-lookup"><span data-stu-id="1b88b-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="1b88b-229">A precedência do `!` operador tem um impacto que pode não ser óbvio.</span><span class="sxs-lookup"><span data-stu-id="1b88b-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="1b88b-230">Se uma função ou operação devolver um valor que seja desembrulhado, a função ou chamada de funcionamento deve ser fechada em parênteses para que o argumento se ligue à chamada e não ao desembrulho.</span><span class="sxs-lookup"><span data-stu-id="1b88b-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="1b88b-231">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b88b-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="1b88b-232">Expressões de matriz</span><span class="sxs-lookup"><span data-stu-id="1b88b-232">Array Expressions</span></span>

<span data-ttu-id="1b88b-233">Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas em suportes quadrados `[]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="1b88b-234">Todos os elementos devem ser compatíveis com o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="1b88b-235">Tendo em conta duas matrizes do mesmo tipo, utilize o operador binário `+` para formar uma nova matriz que é a concatenação das duas matrizes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="1b88b-236">Por exemplo, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="1b88b-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="1b88b-237">Criação de Matrizes</span><span class="sxs-lookup"><span data-stu-id="1b88b-237">Array Creation</span></span>

<span data-ttu-id="1b88b-238">Dado um tipo e uma `Int` expressão, utilize o `new` operador para alocar uma nova matriz do tamanho dado.</span><span class="sxs-lookup"><span data-stu-id="1b88b-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="1b88b-239">Por exemplo, `new Int[i + 1]` atribui uma nova matriz com `Int` `i + 1` elementos.</span><span class="sxs-lookup"><span data-stu-id="1b88b-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="1b88b-240">Não são permitidos conjuntos literais vazios, tais `[]` como, não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="1b88b-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="1b88b-241">Em vez disso, pode criar uma matriz de comprimento zero utilizando `new T[0]` , onde é reservado para um tipo `T` adequado.</span><span class="sxs-lookup"><span data-stu-id="1b88b-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="1b88b-242">Os elementos de uma nova matriz inicializam-se a um valor predefinido dependente do tipo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="1b88b-243">Na maioria dos casos, esta é uma variação de zero.</span><span class="sxs-lookup"><span data-stu-id="1b88b-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="1b88b-244">Para qubits e callables, que são referências a entidades, não existe um valor padrão razoável.</span><span class="sxs-lookup"><span data-stu-id="1b88b-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="1b88b-245">Assim, para estes tipos, o padrão é uma referência inválida que não pode utilizar sem causar um erro de tempo de execução, semelhante a uma referência nula em idiomas como C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="1b88b-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="1b88b-246">Os conjuntos que contenham qubits ou calcáveis devem ser rubricados com valores não predefinidos antes de poder utilizar os seus elementos com segurança.</span><span class="sxs-lookup"><span data-stu-id="1b88b-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="1b88b-247">Para rotinas de inicialização adequadas, consulte <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="1b88b-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="1b88b-248">Os valores predefinidos para cada tipo são:</span><span class="sxs-lookup"><span data-stu-id="1b88b-248">The default values for each type are:</span></span>

<span data-ttu-id="1b88b-249">Tipo</span><span class="sxs-lookup"><span data-stu-id="1b88b-249">Type</span></span> | <span data-ttu-id="1b88b-250">Predefinição</span><span class="sxs-lookup"><span data-stu-id="1b88b-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="1b88b-251">_qubit inválido_</span><span class="sxs-lookup"><span data-stu-id="1b88b-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="1b88b-252">A gama vazia,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="1b88b-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="1b88b-253">_inválido callable_</span><span class="sxs-lookup"><span data-stu-id="1b88b-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="1b88b-254">Os tipos de tuple inicializam elemento por elemento.</span><span class="sxs-lookup"><span data-stu-id="1b88b-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="1b88b-255">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="1b88b-255">Array Elements</span></span>

<span data-ttu-id="1b88b-256">Dada a expressão de matriz e uma `Int` expressão, forme uma nova expressão utilizando o operador de elemento de matriz `[]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="1b88b-257">A nova expressão é do mesmo tipo que o tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="1b88b-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="1b88b-258">Por exemplo, se `a` estiver ligado a uma matriz de `Double` tipo, então `a[4]` é uma `Double` expressão.</span><span class="sxs-lookup"><span data-stu-id="1b88b-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="1b88b-259">Se a expressão da matriz não for um identificador simples, deve pliá-la em parênteses para selecionar um elemento.</span><span class="sxs-lookup"><span data-stu-id="1b88b-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="1b88b-260">Por exemplo, se `a` e `b` são ambas matrizes do `Int` tipo, um elemento da concatenação é expresso como:</span><span class="sxs-lookup"><span data-stu-id="1b88b-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="1b88b-261">Todos os arrays em Q# são baseados em zero.</span><span class="sxs-lookup"><span data-stu-id="1b88b-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="1b88b-262">Ou seja, o primeiro elemento de uma matriz `a` é `a[0]` sempre.</span><span class="sxs-lookup"><span data-stu-id="1b88b-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="1b88b-263">Fatias de Matriz</span><span class="sxs-lookup"><span data-stu-id="1b88b-263">Array Slices</span></span>

<span data-ttu-id="1b88b-264">Dada a expressão de matriz e uma `Range` expressão, forme uma nova expressão utilizando o operador de fatias de matriz `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="1b88b-265">A nova expressão é do mesmo tipo que a matriz e contém os itens de matriz indexados pelos elementos do `Range` , na ordem definida pelo `Range` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="1b88b-266">Por exemplo, se `a` estiver ligado a uma matriz de `Double` tipo, então `a[3..-1..0]` é uma expressão que contém os `Double[]` primeiros quatro elementos de `a` mas na ordem inversa como aparecem em `a` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="1b88b-267">Se a `Range` fatia de matriz estiver vazia, então a fatia de matriz resultante tem um comprimento zero.</span><span class="sxs-lookup"><span data-stu-id="1b88b-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="1b88b-268">Tal como acontece com os elementos de matriz de referência, se a expressão da matriz não for um simples identificador, deve pliá-la em parênteses para a cortar.</span><span class="sxs-lookup"><span data-stu-id="1b88b-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="1b88b-269">Por exemplo, se `a` e `b` são ambos conjuntos de `Int` tipo, uma fatia da concatenação é expressa como:</span><span class="sxs-lookup"><span data-stu-id="1b88b-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="1b88b-270">Valores inferidos de início/fim</span><span class="sxs-lookup"><span data-stu-id="1b88b-270">Inferred start/end values</span></span>

<span data-ttu-id="1b88b-271">Começando com o nosso [lançamento 0.8,](xref:microsoft.quantum.relnotes)apoiamos expressões contextuais para corte de alcance.</span><span class="sxs-lookup"><span data-stu-id="1b88b-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="1b88b-272">Em particular, pode omitir valores de início e fim de alcance no contexto de uma expressão de corte de gama.</span><span class="sxs-lookup"><span data-stu-id="1b88b-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="1b88b-273">Nesse caso, o compilador aplica as seguintes regras para inferir os delimitadores previstos para o intervalo:</span><span class="sxs-lookup"><span data-stu-id="1b88b-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="1b88b-274">Se o valor *inicial* do intervalo for omitido, então o valor inicial inferido</span><span class="sxs-lookup"><span data-stu-id="1b88b-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="1b88b-275">é zero se não for especificado nenhum passo ou se o passo especificado for positivo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="1b88b-276">é o comprimento da matriz fatiada menos um se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="1b88b-277">Se o valor *final* da gama for omitido, então o valor final inferido</span><span class="sxs-lookup"><span data-stu-id="1b88b-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="1b88b-278">é o comprimento da matriz fatiada menos um se não for especificado nenhum passo ou se o passo especificado for positivo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="1b88b-279">é zero se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="1b88b-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="1b88b-280">Alguns exemplos incluem:</span><span class="sxs-lookup"><span data-stu-id="1b88b-280">Some examples are:</span></span>

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="1b88b-281">Expressões de cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="1b88b-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="1b88b-282">Uma vez que todos os tipos Q# são tipos de valor (com os qubits a assumirem um papel um pouco especial), formalmente é criada uma "cópia" quando um valor está ligado a um símbolo ou quando um símbolo é recuperado.</span><span class="sxs-lookup"><span data-stu-id="1b88b-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="1b88b-283">Ou seja, o comportamento de Q# é o mesmo que se uma cópia fosse criada usando um operador de atribuição.</span><span class="sxs-lookup"><span data-stu-id="1b88b-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="1b88b-284">Claro que, na prática, apenas as peças relevantes são recriadas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="1b88b-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="1b88b-285">Isto afeta a forma como copia os arrays porque não é possível atualizar itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="1b88b-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="1b88b-286">Modificar uma matriz existente requer uma alavancagem de um mecanismo *de cópia e atualização.*</span><span class="sxs-lookup"><span data-stu-id="1b88b-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="1b88b-287">Pode criar uma nova matriz a partir de uma matriz existente através de expressões *de cópia e atualização,* que utilizam os operadores `w/` e `<-` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="1b88b-288">Uma expressão de cópia e atualização é uma expressão da `expression1 w/ expression2 <- expression3` forma, onde</span><span class="sxs-lookup"><span data-stu-id="1b88b-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="1b88b-289">`expression1`deve ser tipo `T[]` para algum tipo `T` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="1b88b-290">`expression2`define quais os índices na matriz `expression1` especificados para modificar.</span><span class="sxs-lookup"><span data-stu-id="1b88b-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="1b88b-291">`expression2`deve ser do tipo `Int` ou do tipo `Range` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="1b88b-292">`expression3`é o valor(s) utilizado para atualizar elementos `expression1` em , com base nos índices especificados em `expression2` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="1b88b-293">Se `expression2` for do `Int` tipo, deve ser do tipo `expression3` `T` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="1b88b-294">Se `expression2` for do `Range` tipo, deve ser do tipo `expression3` `T[]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="1b88b-295">Por exemplo, a expressão de cópia e atualização `arr w/ idx <- value` constrói um novo conjunto com todos os elementos definidos para os elementos correspondentes em , exceto nos `arr` elementos(s) especificados por `idx` , que é definido como valor(s) em `value` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="1b88b-296">Dado `arr` contém a `[0,1,2,3]` matriz, então</span><span class="sxs-lookup"><span data-stu-id="1b88b-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="1b88b-297">`arr w/ 0 <- 10`é a matriz `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="1b88b-298">`arr w/ 2 <- 10`é a matriz `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="1b88b-299">`arr w/ 0..2..3 <- [10,12]`é a matriz `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="1b88b-300">Expressões de cópia e atualização para itens nomeados</span><span class="sxs-lookup"><span data-stu-id="1b88b-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="1b88b-301">Expressões semelhantes existem para itens nomeados em tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="1b88b-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="1b88b-302">Por exemplo, considere o tipo</span><span class="sxs-lookup"><span data-stu-id="1b88b-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="1b88b-303">Se `c` contiver o valor do `Complex(1., -1.)` tipo, então `c w/ Re <- 0.` é uma expressão do tipo que avalia `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="1b88b-304">Matrizes irregulares</span><span class="sxs-lookup"><span data-stu-id="1b88b-304">Jagged Arrays</span></span>

<span data-ttu-id="1b88b-305">Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes.</span><span class="sxs-lookup"><span data-stu-id="1b88b-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="1b88b-306">Os elementos de uma matriz irregular podem ser de diferentes tamanhos.</span><span class="sxs-lookup"><span data-stu-id="1b88b-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="1b88b-307">O exemplo a seguir mostra como declarar e inicializar uma matriz irregular que representa uma tabela de multiplicação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="1b88b-308">Matrizes de callables</span><span class="sxs-lookup"><span data-stu-id="1b88b-308">Arrays of callables</span></span> 

<span data-ttu-id="1b88b-309">Também pode criar uma variedade de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1b88b-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="1b88b-310">Se o tipo de elemento comum for um tipo de funcionamento ou função, todos os elementos devem ter os mesmos tipos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="1b88b-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="1b88b-311">O tipo de elemento da matriz suporta quaisquer funtores que sejam [suportados](xref:microsoft.quantum.guide.operationsfunctions) por todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="1b88b-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="1b88b-312">Por exemplo, se `Op1` , e todos são `Op2` `Op3` `Qubit[] => Unit` operações, mas `Op1` `Adjoint` suportes, `Op2` suportes , e apoia `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="1b88b-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="1b88b-313">`[Op1, Op2]`é uma série de `(Qubit[] => Unit)` operações.</span><span class="sxs-lookup"><span data-stu-id="1b88b-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="1b88b-314">`[Op1, Op3]`é uma série de `(Qubit[] => Unit is Adj)` operações.</span><span class="sxs-lookup"><span data-stu-id="1b88b-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="1b88b-315">`[Op2, Op3]`é uma série de `(Qubit[] => Unit is Ctl)` operações.</span><span class="sxs-lookup"><span data-stu-id="1b88b-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="1b88b-316">No entanto, embora as operações `(Qubit[] => Unit is Adj)` e tenham o tipo de base comum `(Qubit[] => Unit is Ctl)` `(Qubit[] => Unit)` de, os *conjuntos destas* operações não partilham um tipo de base comum.</span><span class="sxs-lookup"><span data-stu-id="1b88b-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="1b88b-317">Por exemplo, `[[Op1], [Op2]]` atualmente levantaria um erro porque tenta criar um conjunto dos dois tipos de matrizes incompatíveis `(Qubit[] => Unit is Adj)[]` e `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="1b88b-318">Para obter mais informações sobre chamadas, consulte [expressões callable](#callable-expressions) nesta página ou [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="1b88b-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="1b88b-319">Expressões Condicionais</span><span class="sxs-lookup"><span data-stu-id="1b88b-319">Conditional Expressions</span></span>

<span data-ttu-id="1b88b-320">Tendo em conta duas expressões do mesmo tipo e uma expressão booleana, formam uma expressão condicional utilizando o ponto de `?` interrogação, e a barra `|` vertical.</span><span class="sxs-lookup"><span data-stu-id="1b88b-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="1b88b-321">Dado `a==b ? c | d` que o valor da expressão condicional é se é verdade e se é `c` `a==b` `d` falso.</span><span class="sxs-lookup"><span data-stu-id="1b88b-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="1b88b-322">Expressões condicionais com callables</span><span class="sxs-lookup"><span data-stu-id="1b88b-322">Conditional expressions with callables</span></span>

<span data-ttu-id="1b88b-323">Expressões condicionais podem avaliar operações que tenham as mesmas entradas e saídas, mas suportam diferentes functors.</span><span class="sxs-lookup"><span data-stu-id="1b88b-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="1b88b-324">Neste caso, o tipo de expressão condicional é uma operação com entradas e saídas que suportam quaisquer funtores apoiados por ambas as expressões.</span><span class="sxs-lookup"><span data-stu-id="1b88b-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="1b88b-325">Por exemplo, se `Op1` , e todos são , mas apoiam , apoia , `Op2` e apoia `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="1b88b-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="1b88b-326">`flag ? Op1 | Op2`é uma `(Qubit[] => Unit)` operação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="1b88b-327">`flag ? Op1 | Op3`é uma `(Qubit[] => Unit is Adj)` operação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="1b88b-328">`flag ? Op2 | Op3`é uma `(Qubit[] => Unit is Ctl)` operação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="1b88b-329">Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de funcionamento, essa chamada só ocorre se esse resultado for o valor da chamada.</span><span class="sxs-lookup"><span data-stu-id="1b88b-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="1b88b-330">Por exemplo, no caso `a==b ? C(qs) | D(qs)` , se `a==b` for verdade, a `C` operação é invocada, e se for falsa, então apenas a `D` operação é invocada.</span><span class="sxs-lookup"><span data-stu-id="1b88b-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="1b88b-331">Esta abordagem é semelhante ao *curto-circuito* noutras línguas.</span><span class="sxs-lookup"><span data-stu-id="1b88b-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="1b88b-332">Expressões calláveis</span><span class="sxs-lookup"><span data-stu-id="1b88b-332">Callable Expressions</span></span>

<span data-ttu-id="1b88b-333">Um literal chamado é o nome de uma operação ou função definida no âmbito de compilação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="1b88b-334">Por exemplo, `X` é uma operação literal que se refere à operação padrão da `X` biblioteca, e é uma `Message` função literal que se refere à função de biblioteca `Message` padrão.</span><span class="sxs-lookup"><span data-stu-id="1b88b-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="1b88b-335">Se uma operação suporta o `Adjoint` functor, então `Adjoint op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="1b88b-336">Da mesma forma, se a operação suporta o `Controlled` functor, então `Controlled op` é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="1b88b-337">Para obter mais informações sobre os tipos destas expressões, consulte [as especializações da operação Call](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="1b88b-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="1b88b-338">Os functores `Adjoint` `Controlled` (e) ligam-se mais estreitamente do que todos os outros operadores, com exceção do operador de desembrulhar `!` e da indexação da matriz com `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="1b88b-339">Assim, todos são válidos, assumindo que as operações suportam os funtores utilizados:</span><span class="sxs-lookup"><span data-stu-id="1b88b-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="1b88b-340">Expressões de caloisos por tipo parametrizadas</span><span class="sxs-lookup"><span data-stu-id="1b88b-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="1b88b-341">Você pode usar um literal chamado como um valor, por exemplo, para atribuí-lo a uma variável ou passá-lo para outra chamada.</span><span class="sxs-lookup"><span data-stu-id="1b88b-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="1b88b-342">Neste caso, se a chamada tiver [parâmetros de tipo,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)deve fornecer os parâmetros como parte do valor de chamada.</span><span class="sxs-lookup"><span data-stu-id="1b88b-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="1b88b-343">Um valor calável não pode ter parâmetros de tipo não especificados.</span><span class="sxs-lookup"><span data-stu-id="1b88b-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="1b88b-344">Por exemplo, se `Fun` for uma função com a `'T1->Unit` assinatura:</span><span class="sxs-lookup"><span data-stu-id="1b88b-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="1b88b-345">Expressões de invocação callable</span><span class="sxs-lookup"><span data-stu-id="1b88b-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="1b88b-346">Dada a expressão callable (operação ou função) e uma expressão tuple do tipo de entrada da assinatura do callable, pode formar uma *expressão de invocação,* anexando a expressão de tuple à expressão callable.</span><span class="sxs-lookup"><span data-stu-id="1b88b-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="1b88b-347">O tipo de expressão de invocação é o tipo de saída da assinatura do callable.</span><span class="sxs-lookup"><span data-stu-id="1b88b-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="1b88b-348">Por exemplo, se `Op` for uma operação com a `((Int, Qubit) => Double)` assinatura, é uma expressão do tipo `Op(3, qubit1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="1b88b-349">Da mesma forma, se `Sin` for uma função com a `(Double -> Double)` assinatura, é uma expressão do tipo `Sin(0.1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="1b88b-350">Finalmente, se `Builder` é uma função com a `(Int -> (Int -> Int))` assinatura, então `Builder(3)` é uma função de `Int` `Int` .</span><span class="sxs-lookup"><span data-stu-id="1b88b-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="1b88b-351">Invocar o resultado de uma expressão de valor callable requer um par extra de parênteses em torno da expressão callable.</span><span class="sxs-lookup"><span data-stu-id="1b88b-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="1b88b-352">Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:</span><span class="sxs-lookup"><span data-stu-id="1b88b-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="1b88b-353">Ao invocar uma chamada [tipo-parametrizada,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) pode especificar os parâmetros reais do tipo dentro dos suportes angulares `< >` após a expressão callable.</span><span class="sxs-lookup"><span data-stu-id="1b88b-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="1b88b-354">Esta ação é geralmente desnecessária, uma vez que o compilador Q# infere os tipos reais.</span><span class="sxs-lookup"><span data-stu-id="1b88b-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="1b88b-355">No entanto, *é* necessário para [a aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se um argumento porontose de tipo não for especificado.</span><span class="sxs-lookup"><span data-stu-id="1b88b-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="1b88b-356">Também é útil ao passar operações com diferentes suportes de functor para um callable.</span><span class="sxs-lookup"><span data-stu-id="1b88b-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="1b88b-357">Por exemplo, se `Func` tiver assinatura , e ter assinatura , e tiver assinatura , para invocar `('T1, 'T2, 'T1) -> 'T2` como primeiro `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` `Op1` argumento, como o `Op2` segundo, e como o `Op3` terceiro:</span><span class="sxs-lookup"><span data-stu-id="1b88b-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="1b88b-358">A especificação do tipo é necessária porque `Op3` e `Op1` tem diferentes tipos, de modo que o compilador tratará isto como ambíguo sem a especificação.</span><span class="sxs-lookup"><span data-stu-id="1b88b-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="1b88b-359">Precedência do operador</span><span class="sxs-lookup"><span data-stu-id="1b88b-359">Operator Precedence</span></span>

* <span data-ttu-id="1b88b-360">Todos os operadores binários são associados à direita, `^` exceto.</span><span class="sxs-lookup"><span data-stu-id="1b88b-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="1b88b-361">Os `[ ]` suportes, para corte e indexação de matrizes, ligam-se perante qualquer operador.</span><span class="sxs-lookup"><span data-stu-id="1b88b-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="1b88b-362">Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.</span><span class="sxs-lookup"><span data-stu-id="1b88b-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="1b88b-363">Os parênteses para a invocação de funcionamento e função também se ligam perante qualquer operador, mas após a indexação de matrizes e funtores.</span><span class="sxs-lookup"><span data-stu-id="1b88b-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="1b88b-364">Operadores Q# por ordem de precedência, da mais alta para a mais baixa:</span><span class="sxs-lookup"><span data-stu-id="1b88b-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="1b88b-365">Operador</span><span class="sxs-lookup"><span data-stu-id="1b88b-365">Operator</span></span> | <span data-ttu-id="1b88b-366">Arity</span><span class="sxs-lookup"><span data-stu-id="1b88b-366">Arity</span></span> | <span data-ttu-id="1b88b-367">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b88b-367">Description</span></span> | <span data-ttu-id="1b88b-368">Tipos operand</span><span class="sxs-lookup"><span data-stu-id="1b88b-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="1b88b-369">trailing`!`</span><span class="sxs-lookup"><span data-stu-id="1b88b-369">trailing `!`</span></span> | <span data-ttu-id="1b88b-370">Unária</span><span class="sxs-lookup"><span data-stu-id="1b88b-370">Unary</span></span> | <span data-ttu-id="1b88b-371">Desembrulhar</span><span class="sxs-lookup"><span data-stu-id="1b88b-371">Unwrap</span></span> | <span data-ttu-id="1b88b-372">Qualquer tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="1b88b-372">Any user-defined type</span></span>
 <span data-ttu-id="1b88b-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="1b88b-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="1b88b-374">Unária</span><span class="sxs-lookup"><span data-stu-id="1b88b-374">Unary</span></span> | <span data-ttu-id="1b88b-375">Numérico negativo, complemento bitwise, negação lógica</span><span class="sxs-lookup"><span data-stu-id="1b88b-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="1b88b-376">`Int`, `BigInt` ou `Double` `-` para, ou para `Int` `BigInt` `~~~` , `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="1b88b-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="1b88b-377">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-377">Binary</span></span> | <span data-ttu-id="1b88b-378">Poder inteiro</span><span class="sxs-lookup"><span data-stu-id="1b88b-378">Integer power</span></span> | <span data-ttu-id="1b88b-379">`Int`ou `BigInt` para a base, para o `Int` expoente</span><span class="sxs-lookup"><span data-stu-id="1b88b-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="1b88b-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="1b88b-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="1b88b-381">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-381">Binary</span></span> | <span data-ttu-id="1b88b-382">Divisão, multiplicação, módulo inteiro</span><span class="sxs-lookup"><span data-stu-id="1b88b-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="1b88b-383">`Int`, `BigInt` ou `Double` para `/` `*` e, ou `Int` `BigInt` para`%`</span><span class="sxs-lookup"><span data-stu-id="1b88b-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="1b88b-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="1b88b-384">`+`, `-`</span></span> | <span data-ttu-id="1b88b-385">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-385">Binary</span></span> | <span data-ttu-id="1b88b-386">Adição ou cadeia e concatenação de matriz, subtração</span><span class="sxs-lookup"><span data-stu-id="1b88b-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="1b88b-387">`Int`, `BigInt` ou `Double` , adicionalmente ou qualquer tipo de matriz `String` para`+`</span><span class="sxs-lookup"><span data-stu-id="1b88b-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="1b88b-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="1b88b-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="1b88b-389">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-389">Binary</span></span> | <span data-ttu-id="1b88b-390">Turno da esquerda, turno da direita</span><span class="sxs-lookup"><span data-stu-id="1b88b-390">Left shift, right shift</span></span> | <span data-ttu-id="1b88b-391">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1b88b-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="1b88b-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="1b88b-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="1b88b-393">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-393">Binary</span></span> | <span data-ttu-id="1b88b-394">Comparações menos do que, menos ou iguais, maiores do que, maiores do que iguais</span><span class="sxs-lookup"><span data-stu-id="1b88b-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="1b88b-395">`Int`, `BigInt` ou`Double`</span><span class="sxs-lookup"><span data-stu-id="1b88b-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="1b88b-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="1b88b-396">`==`, `!=`</span></span> | <span data-ttu-id="1b88b-397">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-397">Binary</span></span> | <span data-ttu-id="1b88b-398">comparações iguais e não iguais</span><span class="sxs-lookup"><span data-stu-id="1b88b-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="1b88b-399">qualquer tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="1b88b-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="1b88b-400">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-400">Binary</span></span> | <span data-ttu-id="1b88b-401">Bitwise E</span><span class="sxs-lookup"><span data-stu-id="1b88b-401">Bitwise AND</span></span> | <span data-ttu-id="1b88b-402">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1b88b-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="1b88b-403">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-403">Binary</span></span> | <span data-ttu-id="1b88b-404">Bitwise XOR</span><span class="sxs-lookup"><span data-stu-id="1b88b-404">Bitwise XOR</span></span> | <span data-ttu-id="1b88b-405">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1b88b-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="1b88b-406">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-406">Binary</span></span> | <span data-ttu-id="1b88b-407">Bitwise OR</span><span class="sxs-lookup"><span data-stu-id="1b88b-407">Bitwise OR</span></span> | <span data-ttu-id="1b88b-408">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="1b88b-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="1b88b-409">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-409">Binary</span></span> | <span data-ttu-id="1b88b-410">AND lógico</span><span class="sxs-lookup"><span data-stu-id="1b88b-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="1b88b-411">Binário</span><span class="sxs-lookup"><span data-stu-id="1b88b-411">Binary</span></span> | <span data-ttu-id="1b88b-412">OR lógico</span><span class="sxs-lookup"><span data-stu-id="1b88b-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="1b88b-413">Binário/Ternário</span><span class="sxs-lookup"><span data-stu-id="1b88b-413">Binary/Ternary</span></span> | <span data-ttu-id="1b88b-414">Operador de gama</span><span class="sxs-lookup"><span data-stu-id="1b88b-414">Range operator</span></span> | `Int`
 <span data-ttu-id="1b88b-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="1b88b-415">`?` `|`</span></span> | <span data-ttu-id="1b88b-416">Ternário</span><span class="sxs-lookup"><span data-stu-id="1b88b-416">Ternary</span></span> | <span data-ttu-id="1b88b-417">Condicional</span><span class="sxs-lookup"><span data-stu-id="1b88b-417">Conditional</span></span> | <span data-ttu-id="1b88b-418">`Bool`para o lado esquerdo</span><span class="sxs-lookup"><span data-stu-id="1b88b-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="1b88b-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="1b88b-419">`w/` `<-`</span></span> | <span data-ttu-id="1b88b-420">Ternário</span><span class="sxs-lookup"><span data-stu-id="1b88b-420">Ternary</span></span> | <span data-ttu-id="1b88b-421">Cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="1b88b-421">Copy-and-update</span></span> | <span data-ttu-id="1b88b-422">Ver [expressões de cópia e atualização](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="1b88b-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="1b88b-423">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="1b88b-423">Next steps</span></span>

<span data-ttu-id="1b88b-424">Agora que pode trabalhar com expressões em Q#, passe para [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions) para aprender a definir e chamar operações e funções.</span><span class="sxs-lookup"><span data-stu-id="1b88b-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
