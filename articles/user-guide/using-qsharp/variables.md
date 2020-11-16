---
title: 'Variáveis em Q#'
description: 'Aprenda a trabalhar com diferentes variáveis em Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 67c71c09e004d77360902360fefc7a7752e4a829
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690932"
---
# <a name="variables-in-no-locq"></a><span data-ttu-id="010c6-103">Variáveis em Q#</span><span class="sxs-lookup"><span data-stu-id="010c6-103">Variables in Q#</span></span>

<span data-ttu-id="010c6-104">Q# distingue entre símbolos mutáveis e imutáveis, ou variáveis, que estão *ligadas/atribuídas* a expressões.</span><span class="sxs-lookup"><span data-stu-id="010c6-104">Q# distinguishes between mutable and immutable symbols, or *variables* , which are bound/assigned to expressions.</span></span>
<span data-ttu-id="010c6-105">Em geral, o uso de símbolos imutáveis é encorajado porque permite que o compilador execute mais otimizações.</span><span class="sxs-lookup"><span data-stu-id="010c6-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="010c6-106">O lado esquerdo de uma ligação consiste de um tuple de símbolo e do lado direito de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="010c6-106">The left-hand-side of a binding consists of a symbol tuple and the right-hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="010c6-107">Variáveis Imutáveis</span><span class="sxs-lookup"><span data-stu-id="010c6-107">Immutable Variables</span></span>

<span data-ttu-id="010c6-108">Pode atribuir um valor de qualquer tipo Q# a uma variável para reutilização dentro de uma operação ou função utilizando a `let` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="010c6-108">You can assign a value of any type in Q# to a variable for reuse within an operation or function by using the `let` keyword.</span></span> 

<span data-ttu-id="010c6-109">Uma ligação imutável consiste na palavra-chave, `let` seguida de um símbolo ou tuple de símbolo, um sinal `=` igual, uma expressão para ligar o símbolo(s) e um semicolon de terminante.</span><span class="sxs-lookup"><span data-stu-id="010c6-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="010c6-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="010c6-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="010c6-111">Isto atribui uma matriz específica de operadores Pauli ao nome variável (ou "símbolo"), `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="010c6-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="010c6-112">No exemplo anterior, não há necessidade de especificar explicitamente o tipo da nova variável, uma vez que a expressão no lado direito da `let` declaração é inequívoca, e o compilador infere o tipo correto.</span><span class="sxs-lookup"><span data-stu-id="010c6-112">In the previous example, there is no need to explicitly specify the type of the new variable, as the expression on the right-hand side of the `let` statement is unambiguous, and the compiler infers the correct type.</span></span> 

<span data-ttu-id="010c6-113">As variáveis definidas usando `let` são *imutáveis,* o que significa que uma vez que você defini-lo, você não pode mais mudá-lo de qualquer forma.</span><span class="sxs-lookup"><span data-stu-id="010c6-113">Variables defined using `let` are *immutable* , meaning that once you define it, you can no longer change it in any way.</span></span>
<span data-ttu-id="010c6-114">Isto permite várias otimizações benéficas, incluindo a otimização da lógica clássica que atua sobre variáveis a serem reordenadas para aplicar a `Adjoint` variante de uma operação.</span><span class="sxs-lookup"><span data-stu-id="010c6-114">This allows for several beneficial optimizations, including optimization of the classical logic that acts on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="010c6-115">Variáveis Mutáveis</span><span class="sxs-lookup"><span data-stu-id="010c6-115">Mutable Variables</span></span>

<span data-ttu-id="010c6-116">Como alternativa à criação de uma variável com `let` , a `mutable` palavra-chave cria uma variável mutável que *pode* ser recuperada após a sua criação inicialmente utilizando a `set` palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="010c6-116">As an alternative to creating a variable with `let`, the `mutable` keyword creates a mutable variable that *can* be rebound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="010c6-117">Pode reencambinar os símbolos declarados e vinculados como parte de uma `mutable` declaração a um valor diferente mais tarde no código.</span><span class="sxs-lookup"><span data-stu-id="010c6-117">You can rebind symbols declared and bound as part of a `mutable` statement to a different value later in the code.</span></span> <span data-ttu-id="010c6-118">Se um símbolo for recuperado mais tarde no código, o seu tipo não muda e o valor recém-vinculado deve ser compatível com esse tipo.</span><span class="sxs-lookup"><span data-stu-id="010c6-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value must be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="010c6-119">Reencambraming de símbolos mutáveis</span><span class="sxs-lookup"><span data-stu-id="010c6-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="010c6-120">Pode reencambá-la uma variável mutável usando uma `set` declaração.</span><span class="sxs-lookup"><span data-stu-id="010c6-120">You can rebind a mutable variable using a `set` statement.</span></span>
<span data-ttu-id="010c6-121">Tal reencaminhamento consiste na palavra-chave, `set` seguida de um símbolo ou tuple de símbolo, um sinal `=` igual, uma expressão para reencaminhar o símbolo(s) para, e um semicolon de terminante.</span><span class="sxs-lookup"><span data-stu-id="010c6-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="010c6-122">Seguem-se alguns exemplos de técnicas de afirmação de revindagem.</span><span class="sxs-lookup"><span data-stu-id="010c6-122">The following are some examples of rebinding statement techniques.</span></span>

#### <a name="apply-and-reassign-statements"></a><span data-ttu-id="010c6-123">Aplicar e reatribuir declarações</span><span class="sxs-lookup"><span data-stu-id="010c6-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="010c6-124">Um tipo particular de `set` declaração, a declaração *de aplicação e reatribuição,* proporciona uma forma conveniente de concatenação se o lado direito consistir na aplicação de um operador binário, e o resultado é ser recuperado para o operador o argumento da esquerda.</span><span class="sxs-lookup"><span data-stu-id="010c6-124">A particular kind of `set`-statement, the *apply-and-reassign* statement, provides a convenient way of concatenation if the right-hand side consists of the application of a binary operator, and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="010c6-125">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="010c6-125">For example,</span></span>

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="010c6-126">incrementa o valor do contador `counter` em cada iteração do `for` laço.</span><span class="sxs-lookup"><span data-stu-id="010c6-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="010c6-127">O código anterior é equivalente a</span><span class="sxs-lookup"><span data-stu-id="010c6-127">The previous code is equivalent to</span></span> 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="010c6-128">Estão disponíveis declarações semelhantes para todos os operadores binários em que o tipo do lado esquerdo corresponde ao tipo de expressão.</span><span class="sxs-lookup"><span data-stu-id="010c6-128">Similar statements are available for all binary operators in which the type of the left-hand side matches the expression type.</span></span> <span data-ttu-id="010c6-129">Estas declarações fornecem uma forma conveniente de acumular valores.</span><span class="sxs-lookup"><span data-stu-id="010c6-129">These statements provide a convenient way to accumulate values.</span></span>

<span data-ttu-id="010c6-130">Por exemplo, supondo `qubits` ser um registo de qubits:</span><span class="sxs-lookup"><span data-stu-id="010c6-130">For example, supposing `qubits` is a register of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a><span data-ttu-id="010c6-131">Atualizações e reatribuições</span><span class="sxs-lookup"><span data-stu-id="010c6-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="010c6-132">Existe uma concatenação semelhante para [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) no lado direito.</span><span class="sxs-lookup"><span data-stu-id="010c6-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand side.</span></span>
<span data-ttu-id="010c6-133">Consequentemente, existem declarações *de atualização e reatribuição* para *itens nomeados* em tipos definidos pelo utilizador, bem como para *itens de matriz* .</span><span class="sxs-lookup"><span data-stu-id="010c6-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items* .</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="010c6-134">No caso das matrizes, [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) na Q# biblioteca padrão fornece as ferramentas necessárias para muitas necessidades comuns de inicialização e manipulação de matrizes, ajudando assim a evitar ter de atualizar os itens de matriz em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="010c6-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) in the Q# standard library provides the necessary tools for many common array initialization and manipulation needs, and thus helps avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="010c6-135">As declarações de atualização e reatribuição fornecem uma alternativa, se necessário:</span><span class="sxs-lookup"><span data-stu-id="010c6-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="010c6-136">Utilizando as ferramentas da biblioteca para matrizes fornecidas, [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) pode, por exemplo, definir facilmente uma função que devolve uma série de `Pauli` tipos onde o elemento no índice tem um determinado `i` `Pauli` valor, e todas as outras entradas são a identidade ( `PauliI` ).</span><span class="sxs-lookup"><span data-stu-id="010c6-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays), you can, for example, easily define a function that returns an array of `Pauli` types where the element at index `i` takes a given `Pauli` value, and all other entries are the identity (`PauliI`).</span></span>

<span data-ttu-id="010c6-137">Aqui estão duas definições de tal função, com a segunda a tirar partido das ferramentas à nossa disposição.</span><span class="sxs-lookup"><span data-stu-id="010c6-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

<span data-ttu-id="010c6-138">Em vez de iterar sobre cada índice na matriz, e defini-lo condicionalmente para `PauliI` ou o `pauli` dado, você pode em vez de `ConstantArray` criar uma variedade de [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) `PauliI` tipos, e em seguida, simplesmente devolver uma expressão de cópia e atualização em que você alterou o valor específico no índice `location` :</span><span class="sxs-lookup"><span data-stu-id="010c6-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or the given `pauli`, you can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) to create an array of `PauliI` types, and then simply return a copy-and-update expression in which you've changed the specific value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="010c6-139">Desconstrução de Tuple</span><span class="sxs-lookup"><span data-stu-id="010c6-139">Tuple Deconstruction</span></span>

<span data-ttu-id="010c6-140">Além de atribuir uma única variável, pode utilizar as `let` `mutable` palavras-chave - ou qualquer outra construção vinculativa, como `set` - para desempacotar o conteúdo de um [tipo de tuple](xref:microsoft.quantum.guide.types#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="010c6-140">In addition to assigning a single variable, you can use the `let` and `mutable` keywords - or any other binding construct, such as `set` - to unpack the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="010c6-141">Diz-se que uma atribuição deste formulário *desconstrui* os elementos dessa tuple.</span><span class="sxs-lookup"><span data-stu-id="010c6-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="010c6-142">Se o lado direito da ligação for uma tuple, então pode desconstruir isso após a atribuição.</span><span class="sxs-lookup"><span data-stu-id="010c6-142">If the right-hand side of the binding is a tuple, then you can deconstruct that tuple upon assignment.</span></span>
<span data-ttu-id="010c6-143">Tais desconstruções podem envolver tuples aninhados, e qualquer desconstrução total ou parcial é válida desde que a forma do tuple no lado direito seja compatível com a forma do tuple símbolo.</span><span class="sxs-lookup"><span data-stu-id="010c6-143">Such deconstructions can involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right-hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="010c6-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="010c6-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="010c6-145">Âmbitos de encadernação</span><span class="sxs-lookup"><span data-stu-id="010c6-145">Binding Scopes</span></span>

<span data-ttu-id="010c6-146">Em geral, as ligações dos símbolos ficam fora de alcance e tornam-se inoperantes no final do bloco de declaração em que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="010c6-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="010c6-147">Há duas exceções a esta regra:</span><span class="sxs-lookup"><span data-stu-id="010c6-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="010c6-148">A ligação da variável de laço de um `for` laço está no âmbito do corpo do laço, mas não após o fim do loop.</span><span class="sxs-lookup"><span data-stu-id="010c6-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="010c6-149">Todas as três porções de um `repeat` / `until` laço (o corpo, o teste e a fixação) funcionam como um único âmbito, de modo que os símbolos que estão ligados no corpo estão disponíveis no teste e na fixação.</span><span class="sxs-lookup"><span data-stu-id="010c6-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) act as a single scope, so symbols that are bound in the body are available in the test and the fixup.</span></span>

<span data-ttu-id="010c6-150">Para ambos os tipos de loops, cada passagem através do loop corre no seu próprio âmbito, de modo que as encadernações de um passe anterior não estão disponíveis num passe posterior.</span><span class="sxs-lookup"><span data-stu-id="010c6-150">For both types of loops, each pass through the loop runs in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="010c6-151">Para obter mais informações sobre estes ciclos, consulte [o Control Flow](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="010c6-151">For more information on these loops, see [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="010c6-152">Os blocos internos herdam as ligações dos símbolos dos blocos exteriores.</span><span class="sxs-lookup"><span data-stu-id="010c6-152">Inner blocks inherit symbol bindings from outer blocks.</span></span>
<span data-ttu-id="010c6-153">Só se pode ligar um símbolo uma vez por bloco; é ilegal definir um símbolo com o mesmo nome que outro símbolo que está dentro do âmbito (sem "sombra").</span><span class="sxs-lookup"><span data-stu-id="010c6-153">You can only bind a symbol once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="010c6-154">As seguintes sequências são legais:</span><span class="sxs-lookup"><span data-stu-id="010c6-154">The following sequences are legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="010c6-155">e</span><span class="sxs-lookup"><span data-stu-id="010c6-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="010c6-156">Mas isto seria ilegal:</span><span class="sxs-lookup"><span data-stu-id="010c6-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="010c6-157">como:</span><span class="sxs-lookup"><span data-stu-id="010c6-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a><span data-ttu-id="010c6-158">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="010c6-158">Next steps</span></span>

<span data-ttu-id="010c6-159">Saiba como [trabalhar com qubits](xref:microsoft.quantum.guide.qubits) em Q# .</span><span class="sxs-lookup"><span data-stu-id="010c6-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>