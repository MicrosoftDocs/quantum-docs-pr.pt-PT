---
title: Fluxo de controlo em Q#
description: Laços, condicional, etc.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: 547c57cab67443e8b487bf817eb79fc922b43cdc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833510"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="fd041-103">Fluxo de controlo em Q#</span><span class="sxs-lookup"><span data-stu-id="fd041-103">Control flow in Q#</span></span>

<span data-ttu-id="fd041-104">Dentro de uma operação ou função, cada declaração funciona em ordem, semelhante a outras línguas clássicas imperativas comuns.</span><span class="sxs-lookup"><span data-stu-id="fd041-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="fd041-105">No entanto, pode modificar o fluxo de controlo de três formas distintas:</span><span class="sxs-lookup"><span data-stu-id="fd041-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="fd041-106">`if` declarações</span><span class="sxs-lookup"><span data-stu-id="fd041-106">`if` statements</span></span>
* <span data-ttu-id="fd041-107">`for` loops</span><span class="sxs-lookup"><span data-stu-id="fd041-107">`for` loops</span></span>
* <span data-ttu-id="fd041-108">`repeat-until-success` loops</span><span class="sxs-lookup"><span data-stu-id="fd041-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="fd041-109">conjugações `apply-within` (declarações)</span><span class="sxs-lookup"><span data-stu-id="fd041-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="fd041-110">As `if` construções de fluxo e `for` controlo prosseguem num sentido familiar à maioria das linguagens clássicas de programação.</span><span class="sxs-lookup"><span data-stu-id="fd041-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="fd041-111">[`Repeat-until-success`](#repeat-until-success-loop) loops e conjugações são [discutidos](#conjugations) mais tarde neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fd041-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="fd041-112">Importante, `for` loops e `if` declarações podem ser usados em operações para as quais [as especializações](xref:microsoft.quantum.guide.operationsfunctions) são geradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fd041-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="fd041-113">Nesse cenário, o adjacente de um `for` loop inverte a direção e toma o adjacente de cada iteração.</span><span class="sxs-lookup"><span data-stu-id="fd041-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="fd041-114">Esta ação segue o princípio "sapatos e meias": se quiser desfazer calçar meias e depois sapatos, deve desfazer calçar sapatos e depois desfazer as meias.</span><span class="sxs-lookup"><span data-stu-id="fd041-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="fd041-115">Se, Else-if, Else Else</span><span class="sxs-lookup"><span data-stu-id="fd041-115">If, Else-if, Else</span></span>

<span data-ttu-id="fd041-116">A `if` declaração suporta o processamento condicional.</span><span class="sxs-lookup"><span data-stu-id="fd041-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="fd041-117">Consiste na palavra-chave, `if` uma expressão booleana em parênteses, e um bloco de declaração (o _bloco então)._</span><span class="sxs-lookup"><span data-stu-id="fd041-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="fd041-118">Opcionalmente, qualquer número de outras cláusulas podem seguir- cada uma delas consiste na `elif` palavra-chave , uma expressão booleana em parênteses, e um bloco de declaração (o _bloco de outras partes)._</span><span class="sxs-lookup"><span data-stu-id="fd041-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="fd041-119">Finalmente, a declaração pode, opcionalmente, terminar com outra cláusula, que consiste na palavra-chave `else` seguida por outro bloco de declaração (o _outro_ bloco).</span><span class="sxs-lookup"><span data-stu-id="fd041-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="fd041-120">A `if` condição é avaliada, e se for *verdade,* o *bloco é* executado.</span><span class="sxs-lookup"><span data-stu-id="fd041-120">The `if` condition is evaluated, and if it is *true*, the *then* block is run.</span></span>
<span data-ttu-id="fd041-121">Se a condição for *falsa,* então a primeira condição se for avaliada; se isso é verdade, então o *outro bloco-se* é executado.</span><span class="sxs-lookup"><span data-stu-id="fd041-121">If the condition is *false*, then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="fd041-122">Caso contrário, o segundo bloco se avaliar, e depois o terceiro, e assim por diante, até que uma cláusula com uma condição verdadeira seja encontrada ou não haja mais cláusulas se.</span><span class="sxs-lookup"><span data-stu-id="fd041-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="fd041-123">Se o original *se* a condição e todas as cláusulas se avaliarem *falsas,* o *outro* bloco é executado, se fornecido.</span><span class="sxs-lookup"><span data-stu-id="fd041-123">If the original *if* condition and all the else-if clauses evaluate to *false*, the *else* block is run, if provided.</span></span>

<span data-ttu-id="fd041-124">Note que qualquer que seja o bloco que corre, funciona dentro do seu próprio âmbito.</span><span class="sxs-lookup"><span data-stu-id="fd041-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="fd041-125">As ligações feitas no interior de um `if` bloco , ou bloco não são `elif` `else` visíveis após as extremidades do bloco.</span><span class="sxs-lookup"><span data-stu-id="fd041-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="fd041-126">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="fd041-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="fd041-127">ou</span><span class="sxs-lookup"><span data-stu-id="fd041-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="fd041-128">Ciclos For</span><span class="sxs-lookup"><span data-stu-id="fd041-128">For loop</span></span>

<span data-ttu-id="fd041-129">A `for` declaração suporta a iteração sobre um intervalo inteiro ou uma matriz.</span><span class="sxs-lookup"><span data-stu-id="fd041-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="fd041-130">A afirmação consiste na palavra-chave `for` , seguida de um símbolo ou tuple de símbolo, a palavra-chave , e uma expressão de tipo ou `in` `Range` matriz, tudo em parênteses, e um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="fd041-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="fd041-131">O bloco de declaração (o corpo do laço) funciona repetidamente, com o símbolo definido (a variável loop) ligado a cada valor na gama ou matriz.</span><span class="sxs-lookup"><span data-stu-id="fd041-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="fd041-132">Note que se a expressão de alcance avalia para um alcance ou matriz vazio, o corpo não funciona de todo.</span><span class="sxs-lookup"><span data-stu-id="fd041-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="fd041-133">A expressão é totalmente avaliada antes de entrar no loop, e não muda enquanto o loop está em funcionamento.</span><span class="sxs-lookup"><span data-stu-id="fd041-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="fd041-134">A variável do loop está ligada em cada entrada do corpo em loop, e é desacompida na extremidade do corpo.</span><span class="sxs-lookup"><span data-stu-id="fd041-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="fd041-135">A variável loop não é ligada após o loop for for complete.</span><span class="sxs-lookup"><span data-stu-id="fd041-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="fd041-136">A ligação da variável loop é imutável e segue as mesmas regras que outras encadernações variáveis.</span><span class="sxs-lookup"><span data-stu-id="fd041-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="fd041-137">Nestes exemplos, `qubits` encontra-se um registo de qubits (isto é, do `Qubit[]` tipo),</span><span class="sxs-lookup"><span data-stu-id="fd041-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="fd041-138">Note que no final, utilizamos o operador binário aritmético-esquerdo, `<<<` .</span><span class="sxs-lookup"><span data-stu-id="fd041-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="fd041-139">Para mais informações, consulte [Expressões Numéricas.](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span><span class="sxs-lookup"><span data-stu-id="fd041-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="fd041-140">Loop de repetição até ao sucesso</span><span class="sxs-lookup"><span data-stu-id="fd041-140">Repeat-until-success loop</span></span>

<span data-ttu-id="fd041-141">A Q# linguagem permite que o fluxo de controlo clássico dependa dos resultados da medição de qubits.</span><span class="sxs-lookup"><span data-stu-id="fd041-141">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="fd041-142">Esta capacidade, por sua vez, permite implementar poderosos gadgets probabilísticos que podem reduzir o custo computacional para implementar unitárias.</span><span class="sxs-lookup"><span data-stu-id="fd041-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="fd041-143">Exemplos disso são os padrões *de repetição até ao sucesso* (RUS) em Q# .</span><span class="sxs-lookup"><span data-stu-id="fd041-143">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="fd041-144">Estes padrões RUS são programas probabilísticos que têm um custo baixo *esperado* em termos de portões elementares; o custo incorrido depende da execução real e da interligagem das múltiplas ramificações possíveis.</span><span class="sxs-lookup"><span data-stu-id="fd041-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="fd041-145">Para facilitar os padrões de repetição até ao sucesso (RUS), Q# apoia as construções</span><span class="sxs-lookup"><span data-stu-id="fd041-145">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="fd041-146">onde `expression` é qualquer expressão válida que avalie a um valor de tipo `Bool` .</span><span class="sxs-lookup"><span data-stu-id="fd041-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="fd041-147">O corpo do loop corre, e então a condição é avaliada.</span><span class="sxs-lookup"><span data-stu-id="fd041-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="fd041-148">Se a condição for verdadeira, então a declaração é completada; caso contrário, a correção corre, e a declaração corre novamente, começando com o corpo do laço.</span><span class="sxs-lookup"><span data-stu-id="fd041-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="fd041-149">Todas as três porções de um laço RUS (o corpo, o teste e a fixação) são tratadas como uma única margem *para cada repetição,* pelo que os símbolos que estão ligados ao corpo estão disponíveis tanto no teste como na fixação.</span><span class="sxs-lookup"><span data-stu-id="fd041-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="fd041-150">No entanto, completar o funcionamento da correção termina o âmbito da declaração, de modo que as ligações de símbolos efetuadas durante o corpo ou a correção não estejam disponíveis em repetições subsequentes.</span><span class="sxs-lookup"><span data-stu-id="fd041-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="fd041-151">Além disso, a `fixup` declaração é muitas vezes útil, mas nem sempre necessária.</span><span class="sxs-lookup"><span data-stu-id="fd041-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="fd041-152">Nos casos em que não é necessário, a construção</span><span class="sxs-lookup"><span data-stu-id="fd041-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="fd041-153">é também um padrão RUS válido.</span><span class="sxs-lookup"><span data-stu-id="fd041-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="fd041-154">Para mais exemplos e detalhes, consulte [exemplos de repetição até ao sucesso](#repeat-until-success-examples) neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fd041-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="fd041-155">Evite utilizar laços de repetição até ao sucesso no interior das funções.</span><span class="sxs-lookup"><span data-stu-id="fd041-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="fd041-156">Utilize *enquanto* os loops fornecem as funções correspondentes no interior.</span><span class="sxs-lookup"><span data-stu-id="fd041-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="fd041-157">Ciclo While</span><span class="sxs-lookup"><span data-stu-id="fd041-157">While loop</span></span>

<span data-ttu-id="fd041-158">Os padrões de repetição até ao sucesso têm uma conotação muito quântica específica.</span><span class="sxs-lookup"><span data-stu-id="fd041-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="fd041-159">São amplamente utilizados em determinadas classes de algoritmos quânticos - daí a construção dedicada da linguagem em Q# .</span><span class="sxs-lookup"><span data-stu-id="fd041-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="fd041-160">No entanto, os laços que quebram com base numa condição e cujo comprimento de execução é, portanto, desconhecido no tempo de compilação, são tratados com especial cuidado num tempo de execução quântica.</span><span class="sxs-lookup"><span data-stu-id="fd041-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="fd041-161">No entanto, a sua utilização dentro das funções não é problemática, uma vez que estes loops contêm apenas código que funciona em hardware convencional (não quântico).</span><span class="sxs-lookup"><span data-stu-id="fd041-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="fd041-162">Q#, portanto, suporta a utilização de loops apenas dentro de funções.</span><span class="sxs-lookup"><span data-stu-id="fd041-162">Q#, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="fd041-163">Uma `while` declaração consiste na palavra-chave , uma expressão `while` booleana em parênteses, e um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="fd041-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="fd041-164">O bloco de declaração (o corpo do laço) é executado desde que a condição avalie para `true` .</span><span class="sxs-lookup"><span data-stu-id="fd041-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="fd041-165">Conjugações</span><span class="sxs-lookup"><span data-stu-id="fd041-165">Conjugations</span></span>

<span data-ttu-id="fd041-166">Em contraste com os bits clássicos, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejáveis na computação restante se os qubits ainda estiverem emaranhados.</span><span class="sxs-lookup"><span data-stu-id="fd041-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="fd041-167">Estes efeitos podem ser evitados "desfazendo" os cálculos realizados corretamente antes de libertar a memória.</span><span class="sxs-lookup"><span data-stu-id="fd041-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="fd041-168">Um padrão comum na computação quântica é, por conseguinte, o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd041-168">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="fd041-169">Q# apoia uma declaração de conjugação que implementa a transformação anterior.</span><span class="sxs-lookup"><span data-stu-id="fd041-169">Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="fd041-170">Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="fd041-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="fd041-171">Tal declaração de conjugação torna-se útil se as transformações exteriores e interiores não estiverem prontamente disponíveis como operações, mas são mais convenientes para descrever por um bloco composto por várias declarações.</span><span class="sxs-lookup"><span data-stu-id="fd041-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="fd041-172">A transformação inversa para as declarações definidas no bloco interior é gerada automaticamente pelo compilador e executada após o fim do bloco de aplicação.</span><span class="sxs-lookup"><span data-stu-id="fd041-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="fd041-173">Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente o adjacente do cálculo no bloco interior.</span><span class="sxs-lookup"><span data-stu-id="fd041-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="fd041-174">Declaração de Devolução</span><span class="sxs-lookup"><span data-stu-id="fd041-174">Return Statement</span></span>

<span data-ttu-id="fd041-175">A declaração de devolução termina a execução de uma operação ou função e devolve um valor ao autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="fd041-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="fd041-176">Consiste na palavra-chave, `return` seguida de uma expressão do tipo apropriado, e de um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="fd041-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="fd041-177">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="fd041-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="fd041-178">ou</span><span class="sxs-lookup"><span data-stu-id="fd041-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="fd041-179">Uma chamada que devolve uma tuple vazia, `()` não requer uma declaração de devolução.</span><span class="sxs-lookup"><span data-stu-id="fd041-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="fd041-180">Para especificar uma saída antecipada da operação ou função, utilize `return ();` .</span><span class="sxs-lookup"><span data-stu-id="fd041-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="fd041-181">Os callables que devolvem qualquer outro tipo requerem uma declaração final de devolução.</span><span class="sxs-lookup"><span data-stu-id="fd041-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="fd041-182">Não há um número máximo de declarações de devolução dentro de uma operação.</span><span class="sxs-lookup"><span data-stu-id="fd041-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="fd041-183">O compilador pode emitir um aviso se as declarações seguirem uma declaração de retorno dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="fd041-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="fd041-184">Declaração de falha</span><span class="sxs-lookup"><span data-stu-id="fd041-184">Fail statement</span></span>

<span data-ttu-id="fd041-185">A declaração de falha termina a execução de uma operação e devolve um valor de erro ao autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="fd041-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="fd041-186">Consiste na palavra-chave, `fail` seguida de uma corda e de um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="fd041-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="fd041-187">A declaração devolve a corda ao condutor clássico como mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="fd041-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="fd041-188">Não existe qualquer restrição ao número de declarações de falha no âmbito de uma operação.</span><span class="sxs-lookup"><span data-stu-id="fd041-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="fd041-189">O compilador pode emitir um aviso se as declarações seguirem uma declaração de falha dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="fd041-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="fd041-190">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="fd041-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="fd041-191">ou, utilizando [cordas interpoladas,](xref:microsoft.quantum.guide.expressions#interpolated-strings)</span><span class="sxs-lookup"><span data-stu-id="fd041-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="fd041-192">Exemplos de repetição até ao sucesso</span><span class="sxs-lookup"><span data-stu-id="fd041-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="fd041-193">Padrão RUS para rotação de um único qubit sobre um eixo irracional</span><span class="sxs-lookup"><span data-stu-id="fd041-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="fd041-194">Num caso de uso típico, a seguinte Q# operação implementa uma rotação em torno de um eixo irracional de $(I + 2i Z)/\sqrt {5} $ na esfera Bloch.</span><span class="sxs-lookup"><span data-stu-id="fd041-194">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="fd041-195">A implementação utiliza um padrão RUS conhecido:</span><span class="sxs-lookup"><span data-stu-id="fd041-195">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="fd041-196">Loop RUS com uma variável mutável no âmbito</span><span class="sxs-lookup"><span data-stu-id="fd041-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="fd041-197">Este exemplo mostra a utilização de uma variável mutável, `finished` que está no âmbito de todo o ciclo de repetição até-fixup e que é inicializado antes do loop e atualizado no passo de correção.</span><span class="sxs-lookup"><span data-stu-id="fd041-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="fd041-198">RUS sem `fixup`</span><span class="sxs-lookup"><span data-stu-id="fd041-198">RUS without `fixup`</span></span>

<span data-ttu-id="fd041-199">Este exemplo mostra um loop RUS sem o passo de fixação.</span><span class="sxs-lookup"><span data-stu-id="fd041-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="fd041-200">O código é um circuito probabilístico que implementa um importante portão de rotação $V_3 = (\boldone + 2 i Z) / \sqrt {5} $ usando o `H` e `T` portões.</span><span class="sxs-lookup"><span data-stu-id="fd041-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="fd041-201">O loop termina em repetições de $\frac$ {8} {5} em média.</span><span class="sxs-lookup"><span data-stu-id="fd041-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="fd041-202">Ver [*Repeti-Until-Success: Decomposição não determinística de unitários de um único qubit*](https://arxiv.org/abs/1311.1074) (Paetznick e Svore, 2014) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="fd041-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="fd041-203">RUS para preparar um estado quântico</span><span class="sxs-lookup"><span data-stu-id="fd041-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="fd041-204">Finalmente, aqui está um exemplo de um padrão RUS para preparar um estado quântico $\frac {1} {\sqrt {3} }\left(\sqrt {2} \ket {0} +\ket {1} \right)$, a partir do estado de $\ket{+}$.</span><span class="sxs-lookup"><span data-stu-id="fd041-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="fd041-205">As notáveis características programáticas mostradas nesta operação são:</span><span class="sxs-lookup"><span data-stu-id="fd041-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="fd041-206">Uma parte mais complexa `fixup` do ciclo, que envolve operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="fd041-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="fd041-207">O uso de `AssertMeasurementProbability` declarações para determinar a probabilidade de medir o estado quântico em certos pontos especificados no programa.</span><span class="sxs-lookup"><span data-stu-id="fd041-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="fd041-208">Para obter mais informações sobre o [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) e [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operações, consulte [Testes e depuragem.](xref:microsoft.quantum.guide.testingdebugging)</span><span class="sxs-lookup"><span data-stu-id="fd041-208">For more information about the [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

<span data-ttu-id="fd041-209">Para obter mais informações, consulte [a amostra de teste de unidade fornecida com a biblioteca padrão:](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)</span><span class="sxs-lookup"><span data-stu-id="fd041-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd041-210">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="fd041-210">Next steps</span></span>

<span data-ttu-id="fd041-211">Saiba mais [sobre testes e depuragem](xref:microsoft.quantum.guide.testingdebugging) em Q# .</span><span class="sxs-lookup"><span data-stu-id="fd041-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
