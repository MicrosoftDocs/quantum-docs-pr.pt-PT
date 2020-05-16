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
# <a name="type-expressions-in-q"></a><span data-ttu-id="e9b8e-103">Tipo expressões em Q #</span><span class="sxs-lookup"><span data-stu-id="e9b8e-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="e9b8e-104">Expressões numéricas</span><span class="sxs-lookup"><span data-stu-id="e9b8e-104">Numeric Expressions</span></span>

<span data-ttu-id="e9b8e-105">Expressões numéricas são expressões de `Int` `BigInt` tipo, ou `Double` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="e9b8e-106">Ou são números inteiros ou flutuantes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="e9b8e-107">`Int`os literais em Q# são escritos simplesmente como uma sequência de dígitos.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="e9b8e-108">Os inteiros hexadecimais e binários são suportados com um `0x` `0b` prefixo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="e9b8e-109">`BigInt`os literais em Q# são escritos com um rasto `l` ou `L` sufixo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="e9b8e-110">Os grandes inteiros hexadecimais são suportados com um prefixo "0x".</span><span class="sxs-lookup"><span data-stu-id="e9b8e-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="e9b8e-111">Assim, todos os seguintes são usos válidos de `BigInt` literais:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="e9b8e-112">`Double`os literais em Q# são números de ponto flutuante escritos usando dígitos decimais.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="e9b8e-113">Podem ser escritas com um ponto decimal, `.` e/ou uma parte exponencial indicada com 'e' ou 'E' (após o qual apenas um possível sinal negativo e dígitos decimais são válidos).</span><span class="sxs-lookup"><span data-stu-id="e9b8e-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="e9b8e-114">Seguem-se `Double` os literais válidos: `0.0` . `1.2e5` . `1e-5`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="e9b8e-115">Dada a expressão da matriz de qualquer tipo de elemento, pode ser formada uma `Int` expressão utilizando a [`Length`](xref:microsoft.quantum.core.length) função incorporada, com a expressão da matriz fechada em parênteses, `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="e9b8e-116">Por exemplo, se `a` está ligado a uma matriz, então é uma expressão `Length(a)` inteiro.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="e9b8e-117">Se `b` for um conjunto de conjuntos de inteiros, `Int[][]` então é o número de `Length(b)` sub-arrays em `b` , e é o número de `Length(b[1])` inteiros na segunda sub-matriz em `b` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="e9b8e-118">Tendo em conta duas expressões numéricas do mesmo tipo, os operadores `+` binários, e podem ser `-` `*` `/` usados para formar uma nova expressão numérica.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="e9b8e-119">O tipo da nova expressão será o mesmo que os tipos das expressões constituintes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="e9b8e-120">Tendo em conta duas expressões inteiros, o operador binário `^` (potência) pode ser utilizado para formar uma nova expressão inteiro.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="e9b8e-121">Da mesma forma, `^` pode ser usado com duas expressões duplas para formar uma nova expressão dupla.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="e9b8e-122">Finalmente, `^` pode ser usado com uma grande inteiro à esquerda e um inteiro à direita para formar uma nova grande expressão inteiro.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="e9b8e-123">Neste caso, o segundo parâmetro deve caber em 32 bits; se não, um erro de tempo de execução será levantado.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="e9b8e-124">Tendo em conta duas expressões inteiros ou grandes inteiros, uma nova expressão inteiro ou grande inteiro pode ser formada usando os `%` operadores (modulo), `&&&` (bitwise And), `|||` (bitwise OR), ou `^^^` (bitwise XOR).</span><span class="sxs-lookup"><span data-stu-id="e9b8e-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="e9b8e-125">Dado um inteiro ou uma expressão inteiro à esquerda, e uma expressão inteiro à direita, os `<<<` operadores (mudança de esquerda aritmética) ou `>>>` (mudança de direita aritmética) podem ser usados para criar uma nova expressão com o mesmo tipo que a expressão esquerda.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="e9b8e-126">O segundo parâmetro (o valor de deslocação) para uma das operações por turnos deve ser maior ou igual a zero; o comportamento para quantidades de mudança negativa é indefinido.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="e9b8e-127">O montante de deslocação para qualquer uma das operações por turnos também deve caber em 32 bits; se não, um erro de tempo de execução será levantado.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="e9b8e-128">Se o número a deslocar for um inteiro, então o valor do turno é `mod 64` interpretado; ou seja, uma mudança de 1 e uma mudança de 65 têm o mesmo efeito.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="e9b8e-129">Tanto para valores inteiros como para grandes valores inteiros, as mudanças são aritméticas.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="e9b8e-130">Mudar um valor negativo, quer à esquerda quer à direita, resultará num número negativo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="e9b8e-131">Ou seja, deslocar um passo para a esquerda ou para a direita é exatamente o mesmo que multiplicar ou dividir por 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="e9b8e-132">Divisão integer e modulo inteiro seguem o mesmo comportamento para números negativos que C#.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="e9b8e-133">Ou seja, `a % b` terá sempre o mesmo sinal que , e sempre será igual `a` `b * (a / b) + a % b` `a` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="e9b8e-134">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="e9b8e-135">5</span><span class="sxs-lookup"><span data-stu-id="e9b8e-135">5</span></span> | <span data-ttu-id="e9b8e-136">2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-136">2</span></span> | <span data-ttu-id="e9b8e-137">2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-137">2</span></span> | <span data-ttu-id="e9b8e-138">1</span><span class="sxs-lookup"><span data-stu-id="e9b8e-138">1</span></span>
 <span data-ttu-id="e9b8e-139">5</span><span class="sxs-lookup"><span data-stu-id="e9b8e-139">5</span></span> | <span data-ttu-id="e9b8e-140">-2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-140">-2</span></span> | <span data-ttu-id="e9b8e-141">-2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-141">-2</span></span> | <span data-ttu-id="e9b8e-142">1</span><span class="sxs-lookup"><span data-stu-id="e9b8e-142">1</span></span>
 <span data-ttu-id="e9b8e-143">-5</span><span class="sxs-lookup"><span data-stu-id="e9b8e-143">-5</span></span> | <span data-ttu-id="e9b8e-144">2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-144">2</span></span> | <span data-ttu-id="e9b8e-145">-2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-145">-2</span></span> | <span data-ttu-id="e9b8e-146">-1</span><span class="sxs-lookup"><span data-stu-id="e9b8e-146">-1</span></span>
 <span data-ttu-id="e9b8e-147">-5</span><span class="sxs-lookup"><span data-stu-id="e9b8e-147">-5</span></span> | <span data-ttu-id="e9b8e-148">-2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-148">-2</span></span> | <span data-ttu-id="e9b8e-149">2</span><span class="sxs-lookup"><span data-stu-id="e9b8e-149">2</span></span> | <span data-ttu-id="e9b8e-150">-1</span><span class="sxs-lookup"><span data-stu-id="e9b8e-150">-1</span></span>

<span data-ttu-id="e9b8e-151">A grande divisão de inteiros e o modulo funcionam da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="e9b8e-152">Dada qualquer expressão numérica, pode ser formada uma nova expressão utilizando o `-` operador não-eléctrico.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="e9b8e-153">A nova expressão será do mesmo tipo que a expressão constituinte.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="e9b8e-154">Dada a expressão inteiro ou grande inteiro, pode formar-se uma nova expressão do mesmo tipo utilizando o `~~~` (complemento bitwise) do operador não-secundário.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="e9b8e-155">Expressões booleanas</span><span class="sxs-lookup"><span data-stu-id="e9b8e-155">Boolean Expressions</span></span>

<span data-ttu-id="e9b8e-156">Os dois `Bool` valores literais são `true` `false` e.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="e9b8e-157">Dadas duas expressões do mesmo tipo primitivo, os `==` operadores binários e `!=` binários podem ser utilizados para construir uma `Bool` expressão.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="e9b8e-158">A expressão será verdadeira se as duas expressões forem iguais, e falsas se não forem.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="e9b8e-159">Os valores dos tipos definidos pelo utilizador não podem ser comparados, apenas os seus valores não embrulhados podem ser comparados.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="e9b8e-160">Por exemplo, utilizando o operador "desembrulhar" `!` (explicado em detalhe nos [Tipos em Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span><span class="sxs-lookup"><span data-stu-id="e9b8e-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="e9b8e-161">A comparação da igualdade de `Qubit` valores é a igualdade de identidade; ou seja, se as duas expressões identificam o mesmo qubit.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="e9b8e-162">O estado dos dois qubits não é comparado, acedido, medido ou modificado por esta comparação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="e9b8e-163">A comparação da igualdade de `Double` valores pode ser enganosa devido aos efeitos arredondamentos.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="e9b8e-164">Por exemplo, `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="e9b8e-165">Tendo em conta duas expressões numéricas, os operadores `>` binários, e podem ser `<` `>=` `<=` utilizados para construir uma nova expressão booleana que seja verdadeira se a primeira expressão for respectivamente maior do que, inferior ou igual, ou inferior ou igual ou igual à segunda expressão.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="e9b8e-166">Dadas duas expressões booleanas, os `and` operadores e `or` binários podem ser usados para construir uma nova expressão booleana que é verdade se ambos (resp. ou ambos) as duas expressões forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="e9b8e-167">Dada qualquer expressão booleana, o `not` operador não-secundário pode ser usado para construir uma nova expressão booleana que é verdade se a expressão constituinte for falsa.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="e9b8e-168">Expressões de cordas</span><span class="sxs-lookup"><span data-stu-id="e9b8e-168">String Expressions</span></span>

<span data-ttu-id="e9b8e-169">Q# permite que as cordas sejam utilizadas na `fail` declaração (explicada no [Control Flow)](xref:microsoft.quantum.guide.controlflow#fail-statement)e na [`Message`](xref:microsoft.quantum.intrinsic.message) função padrão.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="e9b8e-170">O comportamento específico deste último depende da aplicação do simulador, mas normalmente escreve uma mensagem para a consola anfitriã quando chamada durante um programa Q#.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="e9b8e-171">As cordas em Q# são literais ou cordas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="e9b8e-172">Os literais de cordas são semelhantes aos simples literais de cordas na maioria das línguas: uma sequência de caracteres Unicode fechados em citações duplas, `"` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="e9b8e-173">Dentro de uma corda, o personagem de corte traseiro pode ser usado para escapar a um personagem de `\` citação dupla, e para inserir uma nova linha como , um retorno de `\n` carruagem como , e um `\r` separador como `\t` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="e9b8e-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="e9b8e-175">Cordas interpoladas</span><span class="sxs-lookup"><span data-stu-id="e9b8e-175">Interpolated strings</span></span>

<span data-ttu-id="e9b8e-176">A sintaxe Q# para interpolações de cordas é um subconjunto da sintaxe C#, mas resumemos aqui os pontos-chave como eles dizem respeito a Q#.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="e9b8e-177">As principais distinções são discutidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="e9b8e-178">Para identificar uma corda literal como uma corda interpolada, prepare-a com o `$` símbolo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="e9b8e-179">Não se pode ter espaço branco entre o `$` e o que começa uma corda `"` literal.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="e9b8e-180">Segue-se um exemplo básico utilizando a [`Message`](xref:microsoft.quantum.intrinsic.message) função para escrever o resultado de uma medição para a consola, ao lado de outras expressões Q#.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="e9b8e-181">Qualquer expressão Q# válida pode aparecer numa corda interpolada.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="e9b8e-182">Mais detalhes sobre a sintaxe C# podem ser encontrados em [*Strings Interpolated*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="e9b8e-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="e9b8e-183">A distinção mais notável é que Q# não suporta cordas interpoladas verbatim (multi-linhas).</span><span class="sxs-lookup"><span data-stu-id="e9b8e-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="e9b8e-184">Expressões dentro de uma corda interpolada seguem Q# sintaxe, não C# sintaxe.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="e9b8e-185">Expressões de alcance</span><span class="sxs-lookup"><span data-stu-id="e9b8e-185">Range Expressions</span></span>

<span data-ttu-id="e9b8e-186">Dadas as três `Int` expressões, e é uma expressão de alcance cujo primeiro elemento é , o segundo elemento é , o `start` terceiro elemento é , `step` `stop` `start .. step .. stop` `start` `start+step` `start+step+step` etc., até `stop` que seja passado.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="e9b8e-187">Uma gama pode estar vazia se, por exemplo, `step` for positiva e `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="e9b8e-188">O último elemento da gama será `stop` se a diferença entre e é um `start` `stop` múltiplo integral `step` de; ou seja, a gama é inclusiva em ambas as extremidades.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="e9b8e-189">Dadas duas `Int` expressões `start` `stop` e, `start .. stop` é uma expressão de alcance que é igual a `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="e9b8e-190">Note que o implícito `step` é +1 mesmo que `stop` seja inferior `start` a; neste caso, o intervalo está vazio.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="e9b8e-191">Algumas gamas de exemplo são:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-191">Some example ranges are:</span></span>

- <span data-ttu-id="e9b8e-192">`1..3`é o intervalo 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="e9b8e-193">`2..2..5`é o intervalo 2, 4.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="e9b8e-194">`2..2..6`é o intervalo 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="e9b8e-195">`6..-2..2`é o alcance 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="e9b8e-196">`2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="e9b8e-197">`2..6..7`é o intervalo 2.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="e9b8e-198">`2..2..1`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="e9b8e-199">`1..-1..2`é o alcance vazio.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="e9b8e-200">Expressões Qubit</span><span class="sxs-lookup"><span data-stu-id="e9b8e-200">Qubit Expressions</span></span>

<span data-ttu-id="e9b8e-201">As `Qubit` únicas expressões são símbolos que estão ligados a `Qubit` valores ou elementos matrizes de `Qubit` matrizes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="e9b8e-202">Não há `Qubit` literal.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="e9b8e-203">Expressões Pauli</span><span class="sxs-lookup"><span data-stu-id="e9b8e-203">Pauli Expressions</span></span>

<span data-ttu-id="e9b8e-204">Os quatro `Pauli` valores, `PauliI` `PauliX` `PauliY` `PauliZ` e, são todas `Pauli` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="e9b8e-205">Além disso, as `Pauli` únicas expressões são símbolos que estão ligados a `Pauli` valores ou elementos matrizes de `Pauli` matrizes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="e9b8e-206">Expressões de Resultados</span><span class="sxs-lookup"><span data-stu-id="e9b8e-206">Result Expressions</span></span>

<span data-ttu-id="e9b8e-207">Os dois `Result` valores, `One` `Zero` e, são `Result` expressões válidas.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="e9b8e-208">Além disso, as `Result` únicas expressões são símbolos que estão ligados a `Result` valores ou elementos matrizes de `Result` matrizes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="e9b8e-209">Em particular, note que não é o mesmo que `One` o inteiro , e não há conversão direta entre `1` eles.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="e9b8e-210">O mesmo se aplica a `Zero` `0` e.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="e9b8e-211">Expressões tuple</span><span class="sxs-lookup"><span data-stu-id="e9b8e-211">Tuple Expressions</span></span>

<span data-ttu-id="e9b8e-212">Um tuple literal é uma sequência de expressões de elementos do tipo apropriado, separadas por vírgulas, fechadas `(` e `)` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="e9b8e-213">Por exemplo, `(1, One)` é uma `(Int, Result)` expressão.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="e9b8e-214">Além dos literais, as únicas expressões de tuple são símbolos que estão ligados a valores de tuple, elementos marray de matrizes de tuple, e invocações calíveis que devolvem tuples.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="e9b8e-215">Expressões de tipo definidas pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="e9b8e-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="e9b8e-216">Um literal de um tipo definido pelo utilizador consiste no nome do tipo seguido de um tuple literal do tipo de tuple base do tipo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="e9b8e-217">Por exemplo, se `IntPair` for um tipo definido pelo utilizador com base, `(Int, Int)` então seria um literal válido desse `IntPair(2, 3)` tipo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="e9b8e-218">Para além dos literais, as únicas expressões de um tipo definido pelo utilizador são símbolos que estão ligados a valores desse tipo, elementos manuais de matrizes desse tipo, e invocações calíveis que devolvem esse tipo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="e9b8e-219">Desembrulhar Expressões</span><span class="sxs-lookup"><span data-stu-id="e9b8e-219">Unwrap Expressions</span></span>

<span data-ttu-id="e9b8e-220">Em Q#, o operador de desembrulhar é um ponto de exclamação de trailing `!` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="e9b8e-221">Por exemplo, se `IntPair` for um tipo definido pelo utilizador com tipo `(Int, Int)` subjacente, e fosse uma `s` variável com `IntPair(2, 3)` valor, então `s!` seria `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="e9b8e-222">Para tipos definidos pelo utilizador definidos em termos de outros tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="e9b8e-223">O operador de desembrulhar pode ser repetido; por exemplo, `s!!` indica o valor duplamente desembrulhado de `s` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="e9b8e-224">Assim, se `WrappedPair` for um tipo definido pelo utilizador com tipo `IntPair` subjacente, e for uma `t` variável com `WrappedPair(IntPair(1,2))` valor, então `t!!` seria `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="e9b8e-225">O operador tem uma precedência maior do que todos os outros operadores que não o índice de `!` `[]` matriz e o corte.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="e9b8e-226">`!`e `[]` ligar posicionalmente; isto é, `a[i]![3]` deve ser lido como : pegue o `((a[i])!)[3]` `i` 'th elemento de , `a` desembrulhe-o, e, em seguida, obtenha o 3º elemento do valor desembrulhado (que deve ser uma matriz).</span><span class="sxs-lookup"><span data-stu-id="e9b8e-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="e9b8e-227">A precedência do `!` operador tem um impacto que pode não ser óbvio.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="e9b8e-228">Se uma função ou operação devolver um valor que depois seja desembrulhado, a função ou chamada de operação deve ser encerrada em parênteses de modo a que o argumento se ligue à chamada e não ao desembrulhar.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="e9b8e-229">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="e9b8e-230">Expressões de matriz</span><span class="sxs-lookup"><span data-stu-id="e9b8e-230">Array Expressions</span></span>

<span data-ttu-id="e9b8e-231">Uma matriz literal é uma sequência de uma ou mais expressões de elementos, separadas por vírgulas, fechadas `[` e `]` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="e9b8e-232">Todos os elementos devem ser compatíveis com o mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-232">All elements must be compatible with the same type.</span></span>


<span data-ttu-id="e9b8e-233">Tendo em conta duas matrizes do mesmo tipo, o operador binário `+` pode ser usado para formar uma nova matriz que é a concatenação das duas matrizes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="e9b8e-234">Por exemplo, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]` é.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="e9b8e-235">Criação de Matriz</span><span class="sxs-lookup"><span data-stu-id="e9b8e-235">Array Creation</span></span>

<span data-ttu-id="e9b8e-236">Dado um tipo e uma `Int` expressão, o `new` operador pode ser utilizado para alocar um novo conjunto do tamanho dado.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="e9b8e-237">Por exemplo, `new Int[i + 1]` atribuiria uma nova `Int` matriz com `i + 1` elementos.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="e9b8e-238">Os elementos de uma nova matriz são inicializados para um valor padrão dependente do tipo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-238">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="e9b8e-239">Na maioria dos casos, esta é uma variação de zero.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-239">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="e9b8e-240">Para qubits e callables, que são referências a entidades, não existe um valor razoável por defeito.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-240">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="e9b8e-241">Assim, para estes tipos, a predefinição é uma referência inválida que não pode ser utilizada sem causar um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-241">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="e9b8e-242">Isto é semelhante a uma referência nula em línguas como C# ou Java.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-242">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="e9b8e-243">As matrizes que contenham qubits ou callables devem ser corretamente inicializadas com valores não predefinidos antes de os seus elementos poderem ser utilizados com segurança.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-243">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="e9b8e-244">Podem ser encontradas rotinas de inicialização adequadas em <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-244">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="e9b8e-245">Os valores predefinidos para cada tipo são:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-245">The default values for each type are:</span></span>

<span data-ttu-id="e9b8e-246">Tipo</span><span class="sxs-lookup"><span data-stu-id="e9b8e-246">Type</span></span> | <span data-ttu-id="e9b8e-247">Predefinição</span><span class="sxs-lookup"><span data-stu-id="e9b8e-247">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="e9b8e-248">_qubit inválido_</span><span class="sxs-lookup"><span data-stu-id="e9b8e-248">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="e9b8e-249">O alcance vazio,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-249">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="e9b8e-250">_inválido callable_</span><span class="sxs-lookup"><span data-stu-id="e9b8e-250">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="e9b8e-251">Os tipos tuple são inicializados elemento a elemento.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-251">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="e9b8e-252">Elementos de matriz</span><span class="sxs-lookup"><span data-stu-id="e9b8e-252">Array Elements</span></span>

<span data-ttu-id="e9b8e-253">Dada a expressão da matriz e uma `Int` expressão, pode formar-se uma nova expressão utilizando o operador de `[` elementos de `]` matriz e matriz.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-253">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="e9b8e-254">A nova expressão será do mesmo tipo que o tipo de elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-254">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="e9b8e-255">Por exemplo, se `a` está ligado a uma série de `Double` s, então `a[4]` é uma `Double` expressão.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-255">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="e9b8e-256">Se a expressão da matriz não for um identificador simples, deve ser fechada em parênteses para selecionar um elemento.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-256">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="e9b8e-257">Por exemplo, se `a` e `b` ambos forem conjuntos de `Int` s, um elemento da concatenação seria expresso como:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-257">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="e9b8e-258">Todas as matrizes em Q# são baseadas em zero.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-258">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="e9b8e-259">Ou seja, o primeiro elemento de uma matriz `a` é `a[0]` sempre.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-259">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="e9b8e-260">Fatias de matriz</span><span class="sxs-lookup"><span data-stu-id="e9b8e-260">Array Slices</span></span>

<span data-ttu-id="e9b8e-261">Dada a expressão da matriz e uma `Range` expressão, pode formar-se uma nova expressão utilizando o operador de `[` fatias de `]` matriz e matriz.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-261">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="e9b8e-262">A nova expressão será do mesmo tipo que a matriz e conterá os itens de matriz indexados pelos elementos do `Range` , na ordem definida pela `Range` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-262">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="e9b8e-263">Por exemplo, se `a` está ligado a uma série de `Double` s, então `a[3..-1..0]` é uma expressão que contém os `Double[]` primeiros quatro elementos de `a` mas na ordem inversa como eles aparecem em `a` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-263">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="e9b8e-264">Se a estiver `Range` vazia, então a fatia de matriz resultante será de zero comprimento.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-264">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="e9b8e-265">Tal como acontece com elementos de matriz referenciais, se a expressão da matriz não for um simples identificador, deve ser fechada a parênteses para cortar.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-265">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="e9b8e-266">Se `a` e ambos são `b` conjuntos de `Int` s, uma fatia da concatenação seria expressa como:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-266">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="e9b8e-267">Valores inferidos de início/fim</span><span class="sxs-lookup"><span data-stu-id="e9b8e-267">Inferred start/end values</span></span>

<span data-ttu-id="e9b8e-268">A partir do nosso lançamento 0.8, apoiamos expressões contextuais para corte de alcance.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-268">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="e9b8e-269">Em particular, os valores de início e fim de gama podem ser omitidos no contexto de uma expressão de corte de gama.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-269">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="e9b8e-270">Nesse caso, o compilador aplicará as seguintes regras para inferir os delimitadores pretendidos para a gama.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-270">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="e9b8e-271">Por exemplo, se o valor de início de gama for omitido, então o valor de início inferido</span><span class="sxs-lookup"><span data-stu-id="e9b8e-271">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="e9b8e-272">é zero se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="e9b8e-272">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="e9b8e-273">é o comprimento da matriz fatiada menos uma se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-273">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="e9b8e-274">Se o valor final do intervalo for omitido, então o valor final inferido</span><span class="sxs-lookup"><span data-stu-id="e9b8e-274">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="e9b8e-275">é o comprimento da matriz fatiada menos um se nenhum passo for especificado ou o passo especificado é positivo, e</span><span class="sxs-lookup"><span data-stu-id="e9b8e-275">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="e9b8e-276">é zero se o passo especificado for negativo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-276">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="e9b8e-277">Expressões de cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="e9b8e-277">Copy-and-Update Expressions</span></span>

<span data-ttu-id="e9b8e-278">Uma vez que todos os tipos de Q# são tipos de valor — com os qubits a assumirem um papel um pouco especial — formalmente é criada uma "cópia" quando um valor está ligado a um símbolo, ou quando um símbolo é recuperado.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-278">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="e9b8e-279">Ou seja, o comportamento do Q# é o mesmo que se uma cópia fosse criada na atribuição.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-279">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="e9b8e-280">É claro que, na prática, apenas as peças relevantes são recriadas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-280">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="e9b8e-281">Isto, em particular, também inclui matrizes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-281">This in particular also includes arrays.</span></span>
<span data-ttu-id="e9b8e-282">Em particular, não é possível atualizar itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-282">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="e9b8e-283">Para modificar uma matriz existente requer alavancar um mecanismo *de cópia e atualização.*</span><span class="sxs-lookup"><span data-stu-id="e9b8e-283">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="e9b8e-284">Novas matrizes podem ser criadas a partir das existentes através de expressões *de cópia e atualização.*</span><span class="sxs-lookup"><span data-stu-id="e9b8e-284">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="e9b8e-285">Uma expressão de cópia e atualização é uma expressão do `expression1 w/ expression2 <- expression3` formulário, onde `expression1` tem de ser de tipo para algum tipo `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-285">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="e9b8e-286">O segundo `expression2` define os índices dos elementos a modificar em comparação com a matriz `expression1` e tem de ser de tipo ou de tipo `Int` `Range` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-286">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="e9b8e-287">Se `expression2` for de `Int` tipo, tem de ser de `expression3` `T` tipo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-287">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="e9b8e-288">Se `expression2` for de `Range` tipo, tem de ser de `expression3` `T[]` tipo.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-288">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="e9b8e-289">Uma expressão de cópia e atualização `arr w/ idx <- value` constrói uma nova matriz com todos os elementos definidos para o elemento correspondente, `arr` com exceção dos elementos em , que `idx` estão definidos para os ou os em `value` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-289">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="e9b8e-290">Por exemplo, se `arr` contiver uma `[0,1,2,3]` matriz, então</span><span class="sxs-lookup"><span data-stu-id="e9b8e-290">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="e9b8e-291">`arr w/ 0 <- 10`é a `[10,1,2,3]` matriz.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-291">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="e9b8e-292">`arr w/ 2 <- 10`é a `[0,1,10,3]` matriz.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-292">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="e9b8e-293">`arr w/ 0..2..3 <- [10,12]`é a `[10,1,12,3]` matriz.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-293">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="e9b8e-294">Expressões de cópia e atualização para itens nomeados</span><span class="sxs-lookup"><span data-stu-id="e9b8e-294">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="e9b8e-295">Existem expressões semelhantes para itens nomeados em tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-295">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="e9b8e-296">Considere, por exemplo, o tipo</span><span class="sxs-lookup"><span data-stu-id="e9b8e-296">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="e9b8e-297">Se `c` contiver o valor do `Complex(1., -1.)` tipo, `c w/ Re <- 0.` então é uma expressão de tipo `Complex` que avalia para `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-297">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="e9b8e-298">Matrizes Irregulares</span><span class="sxs-lookup"><span data-stu-id="e9b8e-298">Jagged Arrays</span></span>

<span data-ttu-id="e9b8e-299">Uma matriz irregular, às vezes chamada de "matrizes", é uma matriz cujos elementos são matrizes.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-299">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="e9b8e-300">Os elementos de uma matriz irregular podem ser de diferentes tamanhos.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-300">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="e9b8e-301">O exemplo que se segue mostra como declarar e inicializar uma matriz irregular representando uma tabela de multiplicação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-301">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="e9b8e-302">Matrizes de callables</span><span class="sxs-lookup"><span data-stu-id="e9b8e-302">Arrays of callables</span></span> 

<span data-ttu-id="e9b8e-303">Note que mais detalhes sobre tipos de callable podem ser encontrados abaixo, bem como na página seguinte, [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="e9b8e-303">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="e9b8e-304">Se o tipo de elemento comum for um tipo de funcionamento ou de função, todos os elementos devem ter os mesmos tipos de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-304">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="e9b8e-305">O tipo de elemento da matriz irá suportar todos os functors que sejam suportados por todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-305">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="e9b8e-306">Por exemplo, se `Op1` , e todos são , mas apoia , apoia , `Op2` e apoia `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-306">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="e9b8e-307">`[Op1, Op2]`é uma série de `(Qubit[] => Unit)` operações.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-307">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="e9b8e-308">`[Op1, Op3]`é uma série de `(Qubit[] => Unit is Adj)` operações.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-308">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="e9b8e-309">`[Op2, Op3]`é uma série de `(Qubit[] => Unit is Ctl)` operações.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-309">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="e9b8e-310">Não são permitidos os literais `[]` vazios.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-310">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="e9b8e-311">Em vez disso, a `new ★[0]` utilização, onde é o espaço reservado para um tipo `★` adequado, permite criar a matriz de comprimento zero desejada.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-311">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="e9b8e-312">Expressões Condicionais</span><span class="sxs-lookup"><span data-stu-id="e9b8e-312">Conditional Expressions</span></span>

<span data-ttu-id="e9b8e-313">Tendo em conta duas outras expressões do mesmo tipo e uma expressão booleana, a expressão condicional pode ser formada utilizando o ponto de interrogação `?` e a barra vertical `|` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-313">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="e9b8e-314">Por exemplo, `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-314">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="e9b8e-315">Neste exemplo, o valor da expressão condicional será `c` se for verdade e se for `a==b` `d` falso.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-315">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="e9b8e-316">Expressões condicionais com callables</span><span class="sxs-lookup"><span data-stu-id="e9b8e-316">Conditional expressions with callables</span></span>

<span data-ttu-id="e9b8e-317">As duas expressões podem avaliar para operações que tenham as mesmas inputs e saídas, mas suportam diferentes functores.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-317">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="e9b8e-318">Neste caso, o tipo de expressão condicional é uma operação com as inputs e saídas que suporta todos os functors suportados por ambas as expressões.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-318">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="e9b8e-319">Por exemplo, se `Op1` , e todos são , mas apoia , apoia , `Op2` e apoia `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` ambos:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-319">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="e9b8e-320">`flag ? Op1 | Op2`é uma `(Qubit[] => Unit)` operação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-320">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="e9b8e-321">`flag ? Op1 | Op3`é uma `(Qubit[] => Unit is Adj)` operação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-321">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="e9b8e-322">`flag ? Op2 | Op3`é uma `(Qubit[] => Unit is Ctl)` operação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-322">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="e9b8e-323">Se uma das duas expressões de resultados possíveis incluir uma função ou chamada de operação, essa chamada só ocorrerá se esse resultado for o valor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-323">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="e9b8e-324">Por exemplo, no `a==b ? C(qs) | D(qs)` caso, se `a==b` for verdade, a operação será `C` invocada, e se for falsa, só `D` será invocada.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-324">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="e9b8e-325">Isto é semelhante ao curto-circuito noutras línguas.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-325">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="e9b8e-326">Expressões Insensíveis</span><span class="sxs-lookup"><span data-stu-id="e9b8e-326">Callable Expressions</span></span>

<span data-ttu-id="e9b8e-327">Um literal calivel é o nome de uma operação ou função definida no âmbito da compilação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-327">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="e9b8e-328">Por exemplo, `X` é uma operação literal que se refere à operação padrão da `X` biblioteca, e é uma `Message` função literal que se refere à função padrão da `Message` biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-328">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="e9b8e-329">Se uma operação suporta o `Adjoint` functor, `Adjoint op` então é uma expressão de operação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-329">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="e9b8e-330">Da mesma forma, se a operação suporta o `Controlled` functor, então é uma expressão de `Controlled op` operação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-330">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="e9b8e-331">Os tipos destas expressões são especificados nas [especializações](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)da operação Call .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-331">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="e9b8e-332">Os functores `Adjoint` (e `Controlled` ) ligam-se mais estreitamente do que todos os outros operadores, com exceção do operador de desembrulhar e da indexação da `!` matriz com []».</span><span class="sxs-lookup"><span data-stu-id="e9b8e-332">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="e9b8e-333">Assim, todos os seguintes são legais, assumindo que as operações apoiam os functors utilizados:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-333">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="e9b8e-334">Expressões de callable parametrizadas tipo</span><span class="sxs-lookup"><span data-stu-id="e9b8e-334">Type-parameterized callable expressions</span></span>

<span data-ttu-id="e9b8e-335">Um literal calivel pode ser usado como um valor, por exemplo, atribuir a uma variável ou passar para outra chamada.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-335">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="e9b8e-336">Neste caso, se o reponsado tiver parâmetros de [tipo,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)devem ser fornecidos como parte do valor calivel.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-336">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="e9b8e-337">Um valor callable não pode ter nenhum tipo de parâmetros não especificados.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-337">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="e9b8e-338">Por exemplo, se `Fun` for uma função com `'T1->Unit` assinatura:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-338">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="e9b8e-339">Expressões de invocação callable</span><span class="sxs-lookup"><span data-stu-id="e9b8e-339">Callable Invocation Expressions</span></span>

<span data-ttu-id="e9b8e-340">Dada uma expressão (operação ou função) insensível e uma expressão de tuple do tipo de entrada da assinatura do callable, uma expressão de invocação pode ser formada através da adesão da expressão de tuple à expressão calúgica.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-340">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="e9b8e-341">O tipo de expressão de invocação é o tipo de saída da assinatura do callable.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-341">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="e9b8e-342">Por exemplo, se `Op` for uma operação com `((Int, Qubit) => Double)` assinatura, é uma expressão de tipo `Op(3, qubit1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-342">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="e9b8e-343">Da mesma forma, se `Sin` for uma função com `(Double -> Double)` assinatura, é uma expressão de tipo `Sin(0.1)` `Double` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-343">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="e9b8e-344">Finalmente, se `Builder` é uma função com `(Int -> (Int -> Int))` assinatura, então `Builder(3)` é uma função de Into to Int.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-344">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="e9b8e-345">Invocar o resultado de uma expressão de valor calivel requer um par extra de parênteses em torno da expressão caluniável.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-345">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="e9b8e-346">Assim, para invocar o resultado da chamada `Builder` do parágrafo anterior, a sintaxe correta é:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-346">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="e9b8e-347">Ao invocar uma chamada de tipo [parametrizada,](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) os parâmetros do tipo real podem ser especificados dentro dos suportes angulares `<` e após a expressão `>` caltável.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-347">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="e9b8e-348">Isto é geralmente desnecessário, uma vez que o compilador Q# inferirá os tipos reais.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-348">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="e9b8e-349">No entanto, *é* necessário para [aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application) se um argumento de tipo paramétrico for deixado não especificado.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-349">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="e9b8e-350">Também é por vezes útil quando se passam operações com diferentes suportes de functor para um callable.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-350">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="e9b8e-351">Por exemplo, se `Func` tiver assinatura , e tiver assinatura , e tiver assinatura , para invocar `('T1, 'T2, 'T1) -> 'T2` como primeiro `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` `Op1` argumento, como o `Op2` segundo, e como o `Op3` terceiro:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-351">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="e9b8e-352">A especificação do tipo é necessária porque `Op3` e `Op1` tem tipos diferentes, por isso o compilador tratará isto como ambíguo sem a especificação.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-352">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="e9b8e-353">Precedência do operador</span><span class="sxs-lookup"><span data-stu-id="e9b8e-353">Operator Precedence</span></span>

<span data-ttu-id="e9b8e-354">Todos os operadores binários são associativos de direito, exceto `^` .</span><span class="sxs-lookup"><span data-stu-id="e9b8e-354">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="e9b8e-355">Os suportes `[` `]` e, para cortar matrize e indexação, ligam-se perante qualquer operador.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-355">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="e9b8e-356">Os functores `Adjoint` e `Controlled` ligam-se após a indexação da matriz, mas antes de todos os outros operadores.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-356">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="e9b8e-357">Os parênteses para a exploração e a invocação de funções também se ligam perante qualquer operador, mas após a indexação da matriz e functores.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-357">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="e9b8e-358">Operadores por ordem de precedência, dos mais elevados aos mais baixos:</span><span class="sxs-lookup"><span data-stu-id="e9b8e-358">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="e9b8e-359">Operador</span><span class="sxs-lookup"><span data-stu-id="e9b8e-359">Operator</span></span> | <span data-ttu-id="e9b8e-360">Rio Arity</span><span class="sxs-lookup"><span data-stu-id="e9b8e-360">Arity</span></span> | <span data-ttu-id="e9b8e-361">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9b8e-361">Description</span></span> | <span data-ttu-id="e9b8e-362">Tipos de operand</span><span class="sxs-lookup"><span data-stu-id="e9b8e-362">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="e9b8e-363">arrastando`!`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-363">trailing `!`</span></span> | <span data-ttu-id="e9b8e-364">Unary</span><span class="sxs-lookup"><span data-stu-id="e9b8e-364">Unary</span></span> | <span data-ttu-id="e9b8e-365">Desembrulhar</span><span class="sxs-lookup"><span data-stu-id="e9b8e-365">Unwrap</span></span> | <span data-ttu-id="e9b8e-366">Qualquer tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="e9b8e-366">Any user-defined type</span></span>
 <span data-ttu-id="e9b8e-367">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-367">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="e9b8e-368">Unary</span><span class="sxs-lookup"><span data-stu-id="e9b8e-368">Unary</span></span> | <span data-ttu-id="e9b8e-369">Negativa numérica, um complemento bitwise, negação lógica</span><span class="sxs-lookup"><span data-stu-id="e9b8e-369">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="e9b8e-370">`Int`, `BigInt` ou `Double` `-` para, ou `Int` `BigInt` `~~~` para, `Bool` para`not`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-370">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="e9b8e-371">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-371">Binary</span></span> | <span data-ttu-id="e9b8e-372">Poder inteiro</span><span class="sxs-lookup"><span data-stu-id="e9b8e-372">Integer power</span></span> | <span data-ttu-id="e9b8e-373">`Int`ou `BigInt` para a base, para o `Int` expoente</span><span class="sxs-lookup"><span data-stu-id="e9b8e-373">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="e9b8e-374">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-374">`/`, `*`, `%`</span></span> | <span data-ttu-id="e9b8e-375">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-375">Binary</span></span> | <span data-ttu-id="e9b8e-376">Divisão, multiplicação, modulo inteiro</span><span class="sxs-lookup"><span data-stu-id="e9b8e-376">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="e9b8e-377">`Int`, `BigInt` ou `Double` para `/` `*` e, ou `Int` `BigInt` para`%`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-377">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="e9b8e-378">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-378">`+`, `-`</span></span> | <span data-ttu-id="e9b8e-379">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-379">Binary</span></span> | <span data-ttu-id="e9b8e-380">Adição ou cadeia e concatenação de cordas, subtração</span><span class="sxs-lookup"><span data-stu-id="e9b8e-380">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="e9b8e-381">`Int`, `BigInt` `Double` ou, adicionalmente ou qualquer tipo de `String` matriz para`+`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-381">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="e9b8e-382">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-382">`<<<`, `>>>`</span></span> | <span data-ttu-id="e9b8e-383">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-383">Binary</span></span> | <span data-ttu-id="e9b8e-384">Turno da esquerda, turno da direita</span><span class="sxs-lookup"><span data-stu-id="e9b8e-384">Left shift, right shift</span></span> | <span data-ttu-id="e9b8e-385">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-385">`Int` or `BigInt`</span></span>
 <span data-ttu-id="e9b8e-386">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-386">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="e9b8e-387">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-387">Binary</span></span> | <span data-ttu-id="e9b8e-388">Comparações menos ou iguais, mais do que iguais, maiores do que iguais ou iguais</span><span class="sxs-lookup"><span data-stu-id="e9b8e-388">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="e9b8e-389">`Int`, `BigInt` ou.`Double`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-389">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="e9b8e-390">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-390">`==`, `!=`</span></span> | <span data-ttu-id="e9b8e-391">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-391">Binary</span></span> | <span data-ttu-id="e9b8e-392">comparações iguais e não iguais</span><span class="sxs-lookup"><span data-stu-id="e9b8e-392">equal, not-equal comparisons</span></span> | <span data-ttu-id="e9b8e-393">qualquer tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="e9b8e-393">any primitive type</span></span>
 `&&&` | <span data-ttu-id="e9b8e-394">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-394">Binary</span></span> | <span data-ttu-id="e9b8e-395">Bitwise E</span><span class="sxs-lookup"><span data-stu-id="e9b8e-395">Bitwise AND</span></span> | <span data-ttu-id="e9b8e-396">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-396">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="e9b8e-397">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-397">Binary</span></span> | <span data-ttu-id="e9b8e-398">Bitwise XOR</span><span class="sxs-lookup"><span data-stu-id="e9b8e-398">Bitwise XOR</span></span> | <span data-ttu-id="e9b8e-399">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-399">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="e9b8e-400">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-400">Binary</span></span> | <span data-ttu-id="e9b8e-401">Bitwise OU</span><span class="sxs-lookup"><span data-stu-id="e9b8e-401">Bitwise OR</span></span> | <span data-ttu-id="e9b8e-402">`Int` ou `BigInt`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-402">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="e9b8e-403">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-403">Binary</span></span> | <span data-ttu-id="e9b8e-404">Lógico E</span><span class="sxs-lookup"><span data-stu-id="e9b8e-404">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="e9b8e-405">Binário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-405">Binary</span></span> | <span data-ttu-id="e9b8e-406">Lógica OU</span><span class="sxs-lookup"><span data-stu-id="e9b8e-406">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="e9b8e-407">Binário/Ternary</span><span class="sxs-lookup"><span data-stu-id="e9b8e-407">Binary/Ternary</span></span> | <span data-ttu-id="e9b8e-408">Operador de gama</span><span class="sxs-lookup"><span data-stu-id="e9b8e-408">Range operator</span></span> | `Int`
 <span data-ttu-id="e9b8e-409">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-409">`?` `|`</span></span> | <span data-ttu-id="e9b8e-410">Ternário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-410">Ternary</span></span> | <span data-ttu-id="e9b8e-411">Condicional</span><span class="sxs-lookup"><span data-stu-id="e9b8e-411">Conditional</span></span> | <span data-ttu-id="e9b8e-412">`Bool`para o lado esquerdo</span><span class="sxs-lookup"><span data-stu-id="e9b8e-412">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="e9b8e-413">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="e9b8e-413">`w/` `<-`</span></span> | <span data-ttu-id="e9b8e-414">Ternário</span><span class="sxs-lookup"><span data-stu-id="e9b8e-414">Ternary</span></span> | <span data-ttu-id="e9b8e-415">Cópia e atualização</span><span class="sxs-lookup"><span data-stu-id="e9b8e-415">Copy-and-update</span></span> | <span data-ttu-id="e9b8e-416">ver [expressões de cópia e atualização](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="e9b8e-416">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="whats-next"></a><span data-ttu-id="e9b8e-417">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="e9b8e-417">What's Next?</span></span>
<span data-ttu-id="e9b8e-418">Agora que pode trabalhar com expressões em Q#, pode dirigir-se a [Operações e Funções em Q#](xref:microsoft.quantum.guide.operationsfunctions) para aprender a definir e chamar operações e funções.</span><span class="sxs-lookup"><span data-stu-id="e9b8e-418">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
