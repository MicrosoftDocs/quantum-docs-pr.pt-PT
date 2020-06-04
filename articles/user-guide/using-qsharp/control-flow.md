---
title: 'Fluxo de controlo em Q #'
description: Laços, condicional, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326545"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="236ce-103">Fluxo de controlo em Q #</span><span class="sxs-lookup"><span data-stu-id="236ce-103">Control Flow in Q#</span></span>

<span data-ttu-id="236ce-104">Dentro de uma operação ou função, cada declaração executa por ordem, semelhante à linguagem clássica mais comum.</span><span class="sxs-lookup"><span data-stu-id="236ce-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="236ce-105">No entanto, este fluxo de controlo pode ser modificado de três formas distintas:</span><span class="sxs-lookup"><span data-stu-id="236ce-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="236ce-106">`if`declarações</span><span class="sxs-lookup"><span data-stu-id="236ce-106">`if` statements</span></span>
- <span data-ttu-id="236ce-107">`for`loops</span><span class="sxs-lookup"><span data-stu-id="236ce-107">`for` loops</span></span>
- <span data-ttu-id="236ce-108">`repeat`-`until`loops</span><span class="sxs-lookup"><span data-stu-id="236ce-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="236ce-109">Adiamos a discussão deste último para [mais abaixo.](#repeat-until-success-loop)</span><span class="sxs-lookup"><span data-stu-id="236ce-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="236ce-110">O `if` fluxo e o fluxo de `for` controlo, no entanto, procedem num sentido familiar à maioria das linguagens clássicas de programação.</span><span class="sxs-lookup"><span data-stu-id="236ce-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="236ce-111">É importante que `for` os loops e `if` as declarações possam ser utilizados em operações para as quais as especializações são geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="236ce-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="236ce-112">Nesse caso, o adjacente de um `for` laço inverte a direção e toma o adjacente de cada iteração.</span><span class="sxs-lookup"><span data-stu-id="236ce-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="236ce-113">Isto segue o princípio "sapatos e meias": se quiser desfazer calçar meias e depois sapatos, deve desfazer calçar sapatos e depois desfazer as meias.</span><span class="sxs-lookup"><span data-stu-id="236ce-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="236ce-114">Funciona decididamente menos bem para tentar tirar as meias enquanto ainda usa os sapatos!</span><span class="sxs-lookup"><span data-stu-id="236ce-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="236ce-115">Se, Else-if, Else Else</span><span class="sxs-lookup"><span data-stu-id="236ce-115">If, Else-if, Else</span></span>

<span data-ttu-id="236ce-116">A `if` declaração apoia a execução condicional.</span><span class="sxs-lookup"><span data-stu-id="236ce-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="236ce-117">Consiste na palavra-chave `if` , um parênteses `(` aberto, uma expressão booleana, um parênteses `)` próximos, e um bloco de afirmação (o _bloco então)._</span><span class="sxs-lookup"><span data-stu-id="236ce-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="236ce-118">Isto pode ser seguido por qualquer número de outras cláusulas, cada uma das quais consiste na palavra-chave `elif` , um parênteses aberto `(` , uma expressão booleana, um parênteses `)` próximos , e um bloco de declaração (o _bloco de outras partes)._</span><span class="sxs-lookup"><span data-stu-id="236ce-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="236ce-119">Finalmente, a declaração pode, opcionalmente, terminar com outra cláusula, que consiste na palavra-chave `else` seguida por outro bloco de declaração (o _outro_ bloco).</span><span class="sxs-lookup"><span data-stu-id="236ce-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="236ce-120">A `if` condição é avaliada, e se for verdade, o bloco é executado.</span><span class="sxs-lookup"><span data-stu-id="236ce-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="236ce-121">Se a condição for falsa, então a primeira condição se for avaliada; se for verdade, o outro bloco é executado.</span><span class="sxs-lookup"><span data-stu-id="236ce-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="236ce-122">Caso contrário, o segundo bloco se for testado, e depois o terceiro, e assim por diante, até que uma cláusula com uma condição verdadeira seja encontrada ou não haja mais cláusulas se.</span><span class="sxs-lookup"><span data-stu-id="236ce-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="236ce-123">Se a condição original e todas as outras cláusulas avaliarem falsas, o outro bloco é executado se um for fornecido.</span><span class="sxs-lookup"><span data-stu-id="236ce-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="236ce-124">Note que qualquer bloco executado é executado no seu próprio âmbito.</span><span class="sxs-lookup"><span data-stu-id="236ce-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="236ce-125">As encadernações feitas no interior de um `if` bloco , ou bloco não são `elif` `else` visíveis após o seu fim.</span><span class="sxs-lookup"><span data-stu-id="236ce-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="236ce-126">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="236ce-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="236ce-127">ou</span><span class="sxs-lookup"><span data-stu-id="236ce-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="236ce-128">Para Loop</span><span class="sxs-lookup"><span data-stu-id="236ce-128">For Loop</span></span>

<span data-ttu-id="236ce-129">A `for` declaração suporta a iteração sobre um intervalo inteiro ou sobre uma matriz.</span><span class="sxs-lookup"><span data-stu-id="236ce-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="236ce-130">A afirmação consiste na palavra-chave `for` , um parênteses `(` aberto, seguido de um símbolo ou tuple de símbolo, a palavra-chave `in` , uma expressão de tipo ou `Range` matriz, um parênteses `)` próximos , e um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="236ce-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="236ce-131">O bloco de afirmação (o corpo do laço) é executado repetidamente, com o símbolo ou(s) (s) variável de loop(s) ligado a cada valor na gama ou matriz.</span><span class="sxs-lookup"><span data-stu-id="236ce-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="236ce-132">Note que se a expressão de alcance avaliar para um alcance ou matriz vazio, o corpo não será executado de todo.</span><span class="sxs-lookup"><span data-stu-id="236ce-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="236ce-133">A expressão é totalmente avaliada antes de entrar no loop, e não mudará enquanto o loop estiver a ser executado.</span><span class="sxs-lookup"><span data-stu-id="236ce-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="236ce-134">A variável do loop é ligada em cada entrada para o corpo em loop, e desacompida na extremidade do corpo.</span><span class="sxs-lookup"><span data-stu-id="236ce-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="236ce-135">Em particular, a variável loop não é ligada após a conclusão do loop.</span><span class="sxs-lookup"><span data-stu-id="236ce-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="236ce-136">A ligação dos símbolos declarados é imutável e segue as mesmas regras que outras ligações variáveis.</span><span class="sxs-lookup"><span data-stu-id="236ce-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="236ce-137">Em alguns exemplos, supondo `qubits` ser um registo de qubits (isto é, do `Qubit[]` tipo),</span><span class="sxs-lookup"><span data-stu-id="236ce-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
<span data-ttu-id="236ce-138">Note que no final utilizamos o operador binário aritmético-esquerdo, `<<<` cujos detalhes podem ser encontrados em [Expressões Numéricas](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span><span class="sxs-lookup"><span data-stu-id="236ce-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="236ce-139">Loop de repetição até ao sucesso</span><span class="sxs-lookup"><span data-stu-id="236ce-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="236ce-140">A linguagem Q# permite que o fluxo de controlo clássico dependa dos resultados da medição de qubits.</span><span class="sxs-lookup"><span data-stu-id="236ce-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="236ce-141">Esta capacidade, por sua vez, permite implementar poderosos gadgets probabilísticos que podem reduzir o custo computacional para implementar unitárias.</span><span class="sxs-lookup"><span data-stu-id="236ce-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="236ce-142">Como exemplo, é fácil implementar os chamados padrões *Repeat-Until-Success* (RUS) em Q#.</span><span class="sxs-lookup"><span data-stu-id="236ce-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="236ce-143">Estes padrões RUS são programas probabilísticos que têm um custo baixo *esperado* em termos de portões elementares, mas para os quais o verdadeiro custo depende de uma execução real e de uma interleling real de várias ramificações possíveis.</span><span class="sxs-lookup"><span data-stu-id="236ce-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="236ce-144">Para facilitar os padrões de Repetição-Até-Sucesso (RUS), Q# suporta as construções</span><span class="sxs-lookup"><span data-stu-id="236ce-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="236ce-145">onde `expression` é qualquer expressão válida que avalie a um valor de tipo `Bool` .</span><span class="sxs-lookup"><span data-stu-id="236ce-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="236ce-146">O corpo em loop é executado, e então a condição é avaliada.</span><span class="sxs-lookup"><span data-stu-id="236ce-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="236ce-147">Se a condição for verdadeira, então a declaração é completada; caso contrário, a correção é executada, e a declaração é re-executada a partir do corpo do laço.</span><span class="sxs-lookup"><span data-stu-id="236ce-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="236ce-148">Todas as três porções de um ciclo de repetição/até loop (o corpo, o teste e a fixação) são tratadas como uma única margem *para cada repetição,* pelo que os símbolos que estão ligados ao corpo estão disponíveis no teste e na fixação.</span><span class="sxs-lookup"><span data-stu-id="236ce-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="236ce-149">No entanto, a conclusão da execução da correção termina o âmbito da declaração, de modo a que as ligações de símbolos efetuadas durante o corpo ou a correção não estejam disponíveis em repetições subsequentes.</span><span class="sxs-lookup"><span data-stu-id="236ce-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="236ce-150">Além disso, a `fixup` declaração é muitas vezes útil, mas nem sempre necessária.</span><span class="sxs-lookup"><span data-stu-id="236ce-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="236ce-151">Nos casos em que não é necessário, a construção</span><span class="sxs-lookup"><span data-stu-id="236ce-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="236ce-152">é também um padrão RUS válido.</span><span class="sxs-lookup"><span data-stu-id="236ce-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="236ce-153">Na parte inferior desta página apresentamos [alguns exemplos de loops RUS](#repeat-until-success-examples).</span><span class="sxs-lookup"><span data-stu-id="236ce-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="236ce-154">Evite utilizar laços de repetição até ao sucesso no interior das funções.</span><span class="sxs-lookup"><span data-stu-id="236ce-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="236ce-155">A funcionalidade correspondente é fornecida por loops em funções.</span><span class="sxs-lookup"><span data-stu-id="236ce-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="236ce-156">Enquanto Loop</span><span class="sxs-lookup"><span data-stu-id="236ce-156">While Loop</span></span>

<span data-ttu-id="236ce-157">Os padrões de repetição até ao sucesso têm uma conotação muito quântica específica.</span><span class="sxs-lookup"><span data-stu-id="236ce-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="236ce-158">São amplamente utilizados em classes particulares de algoritmos quânticos, daí a construção dedicada da linguagem em Q#.</span><span class="sxs-lookup"><span data-stu-id="236ce-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="236ce-159">No entanto, os laços que quebram com base numa condição e cujo comprimento de execução é, portanto, desconhecido no tempo de compilação, precisam de ser tratados com especial cuidado num tempo de execução quântica.</span><span class="sxs-lookup"><span data-stu-id="236ce-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="236ce-160">A sua utilização dentro de funções, por outro lado, não é problemática, uma vez que estas contêm apenas código que será executado em hardware convencional (não quântico).</span><span class="sxs-lookup"><span data-stu-id="236ce-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="236ce-161">Q# Portanto, suporta a utilização de loops apenas dentro de funções.</span><span class="sxs-lookup"><span data-stu-id="236ce-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="236ce-162">Uma `while` declaração consiste na palavra-chave , um `while` parênteses `(` aberto, uma condição (ou seja, uma expressão booleana), um parênteses `)` próximos , e um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="236ce-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="236ce-163">O bloco de declaração (o corpo do laço) é executado desde que a condição avalie a `true` .</span><span class="sxs-lookup"><span data-stu-id="236ce-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="236ce-164">Declaração de Devolução</span><span class="sxs-lookup"><span data-stu-id="236ce-164">Return Statement</span></span>

<span data-ttu-id="236ce-165">A declaração de devolução termina a execução de uma operação ou função e devolve um valor ao autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="236ce-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="236ce-166">Consiste na palavra-chave, `return` seguida de uma expressão do tipo apropriado, e de um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="236ce-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="236ce-167">Uma chamada que devolve uma tuple vazia, `()` não requer uma declaração de devolução.</span><span class="sxs-lookup"><span data-stu-id="236ce-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="236ce-168">Se desejar uma saída antecipada, `return ()` pode ser utilizada neste caso.</span><span class="sxs-lookup"><span data-stu-id="236ce-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="236ce-169">Os callables que devolvem qualquer outro tipo requerem uma declaração final de devolução.</span><span class="sxs-lookup"><span data-stu-id="236ce-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="236ce-170">Não há um número máximo de declarações de devolução dentro de uma operação.</span><span class="sxs-lookup"><span data-stu-id="236ce-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="236ce-171">O compilador pode emitir um aviso se as declarações seguirem uma declaração de retorno dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="236ce-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="236ce-172">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="236ce-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="236ce-173">ou</span><span class="sxs-lookup"><span data-stu-id="236ce-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="236ce-174">ou</span><span class="sxs-lookup"><span data-stu-id="236ce-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="236ce-175">Declaração de Falha</span><span class="sxs-lookup"><span data-stu-id="236ce-175">Fail Statement</span></span>

<span data-ttu-id="236ce-176">A declaração de falha termina a execução de uma operação e devolve um valor de erro ao autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="236ce-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="236ce-177">Consiste na palavra-chave, `fail` seguida de uma corda e de um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="236ce-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="236ce-178">A corda é devolvida ao condutor clássico como mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="236ce-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="236ce-179">Não existe qualquer restrição ao número de declarações de falha no âmbito de uma operação.</span><span class="sxs-lookup"><span data-stu-id="236ce-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="236ce-180">O compilador pode emitir um aviso se as declarações seguirem uma declaração de falha dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="236ce-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="236ce-181">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="236ce-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="236ce-182">ou, utilizando [cordas interpoladas,](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="236ce-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="236ce-183">Exemplos de repetição até ao sucesso</span><span class="sxs-lookup"><span data-stu-id="236ce-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="236ce-184">Padrão RUS para rotação de um único qubit sobre um eixo irracional</span><span class="sxs-lookup"><span data-stu-id="236ce-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="236ce-185">Num caso de uso típico, a seguinte operação Q# implementa uma rotação em torno de um eixo irracional de $(I + 2i Z)/\sqrt {5} $ na esfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="236ce-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="236ce-186">Isto é conseguido usando um padrão RUS conhecido:</span><span class="sxs-lookup"><span data-stu-id="236ce-186">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="236ce-187">Loop RUS com variável mutável no âmbito</span><span class="sxs-lookup"><span data-stu-id="236ce-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="236ce-188">Este exemplo mostra a utilização de uma variável mutável `finished` que está no âmbito de todo o ciclo de repetição até à fixação e que é inicializado antes do loop e atualizado no passo de fixação.</span><span class="sxs-lookup"><span data-stu-id="236ce-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="236ce-189">RUS sem`fixup`</span><span class="sxs-lookup"><span data-stu-id="236ce-189">RUS without `fixup`</span></span>

<span data-ttu-id="236ce-190">Por exemplo, o seguinte código é um circuito probabilístico que implementa um importante portão de rotação $V_3 = (\boldone + 2 i Z) / \sqrt {5} $ usando o `H` e `T` portões.</span><span class="sxs-lookup"><span data-stu-id="236ce-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="236ce-191">O loop termina em repetições de $\frac$ {8} {5} em média.</span><span class="sxs-lookup"><span data-stu-id="236ce-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="236ce-192">Ver [*Repeti-Until-Success: Decomposição não determinística de unitários de um único qubit*](https://arxiv.org/abs/1311.1074) (Paetznick e Svore, 2014) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="236ce-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="236ce-193">RUS para preparar um estado quântico</span><span class="sxs-lookup"><span data-stu-id="236ce-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="236ce-194">Finalmente, mostramos um exemplo de um padrão RUS para preparar um estado quântico $\frac {1} {\sqrt {3} }\left(\sqrt {2} \ket {0} +\ket {1} \right)$, a partir do estado de $\ket{+}$.</span><span class="sxs-lookup"><span data-stu-id="236ce-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="236ce-195">Consulte também a [amostra de teste de unidade fornecida com a biblioteca padrão:](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)</span><span class="sxs-lookup"><span data-stu-id="236ce-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="236ce-196">Notáveis características programáticas mostradas nesta operação são uma parte mais complexa `fixup` do loop, que envolve operações quânticas, e o uso de `AssertProb` declarações para determinar a probabilidade de medir o estado quântico em certos pontos especificados no programa.</span><span class="sxs-lookup"><span data-stu-id="236ce-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="236ce-197">Consulte também [os Testes e depurando](xref:microsoft.quantum.guide.testingdebugging) para obter mais informações sobre o [`Assert`](xref:microsoft.quantum.intrinsic.assert) e [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operações.</span><span class="sxs-lookup"><span data-stu-id="236ce-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="236ce-198">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="236ce-198">Next steps</span></span>

<span data-ttu-id="236ce-199">Saiba mais [sobre Testes e Debugging](xref:microsoft.quantum.guide.testingdebugging) em Q#.</span><span class="sxs-lookup"><span data-stu-id="236ce-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>