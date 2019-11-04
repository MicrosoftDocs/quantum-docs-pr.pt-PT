---
title: 'Instruções Q # | Microsoft Docs'
description: 'Instruções Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184870"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="9075e-103">Instruções e outras construções</span><span class="sxs-lookup"><span data-stu-id="9075e-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="9075e-104">Comentários</span><span class="sxs-lookup"><span data-stu-id="9075e-104">Comments</span></span>

<span data-ttu-id="9075e-105">Os comentários começam com duas barras, `//`e continuam até o fim da linha.</span><span class="sxs-lookup"><span data-stu-id="9075e-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="9075e-106">Um comentário pode aparecer em qualquer lugar em um arquivo de origem Q #.</span><span class="sxs-lookup"><span data-stu-id="9075e-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="9075e-107">Comentários da documentação</span><span class="sxs-lookup"><span data-stu-id="9075e-107">Documentation Comments</span></span>

<span data-ttu-id="9075e-108">Os comentários que começam com três barras "/", `///`, são tratados especialmente pelo compilador quando aparecem imediatamente antes de um namespace, operação, especialização, função ou definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="9075e-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="9075e-109">Nesse caso, seu conteúdo é levado como documentação para o tipo definido pelo usuário ou callable, como para outras linguagens .NET.</span><span class="sxs-lookup"><span data-stu-id="9075e-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="9075e-110">Em `///` comentários, o texto a ser exibido como parte da documentação da API é formatado como [redução](https://daringfireball.net/projects/markdown/syntax), com partes diferentes da documentação que está sendo indicada por cabeçalhos nomeados especialmente.</span><span class="sxs-lookup"><span data-stu-id="9075e-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="9075e-111">Como uma extensão para redução, referências cruzadas a operações, funções e tipos definidos pelo usuário em Q # podem ser incluídas usando o `@"<ref target>"`, onde `<ref target>` é substituído pelo nome totalmente qualificado do objeto de código que está sendo referenciado.</span><span class="sxs-lookup"><span data-stu-id="9075e-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="9075e-112">Opcionalmente, um mecanismo de documentação também pode oferecer suporte a extensões de redução adicionais.</span><span class="sxs-lookup"><span data-stu-id="9075e-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="9075e-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9075e-113">For example:</span></span>

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

<span data-ttu-id="9075e-114">Os nomes a seguir são reconhecidos como cabeçalhos de comentário da documentação.</span><span class="sxs-lookup"><span data-stu-id="9075e-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="9075e-115">**Resumo**: um breve resumo do comportamento de uma função ou operação, ou da finalidade de um tipo.</span><span class="sxs-lookup"><span data-stu-id="9075e-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="9075e-116">O primeiro parágrafo do resumo é usado para informações de foco.</span><span class="sxs-lookup"><span data-stu-id="9075e-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="9075e-117">Ele deve ser texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="9075e-117">It should be plain text.</span></span>
- <span data-ttu-id="9075e-118">**Descrição**: uma descrição do comportamento de uma função ou operação, ou da finalidade de um tipo.</span><span class="sxs-lookup"><span data-stu-id="9075e-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="9075e-119">O resumo e a descrição são concatenados para formar o arquivo de documentação gerado para a função, a operação ou o tipo.</span><span class="sxs-lookup"><span data-stu-id="9075e-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="9075e-120">A descrição pode conter símbolos e equações LaTeX e formatados em linha.</span><span class="sxs-lookup"><span data-stu-id="9075e-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="9075e-121">**Entrada**: uma descrição da tupla de entrada para uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="9075e-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="9075e-122">Pode conter subseções de redução adicionais indicando cada elemento individual da tupla de entrada.</span><span class="sxs-lookup"><span data-stu-id="9075e-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="9075e-123">**Saída**: uma descrição da tupla retornada por uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="9075e-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="9075e-124">**Parâmetros de tipo**: uma seção vazia que contém uma subseção adicional para cada parâmetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="9075e-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="9075e-125">**Exemplo**: um breve exemplo da operação, função ou tipo em uso.</span><span class="sxs-lookup"><span data-stu-id="9075e-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="9075e-126">**Comentários**: o Proseware variado que descreve algum aspecto da operação, função ou tipo.</span><span class="sxs-lookup"><span data-stu-id="9075e-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="9075e-127">**Consulte também**: uma lista de nomes totalmente qualificados que indica funções relacionadas, operações ou tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="9075e-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="9075e-128">**Referências**: uma lista de referências e citações para o item que está sendo documentado.</span><span class="sxs-lookup"><span data-stu-id="9075e-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="9075e-129">Espaços de nomes</span><span class="sxs-lookup"><span data-stu-id="9075e-129">Namespaces</span></span>

<span data-ttu-id="9075e-130">Cada operação de Q #, função e tipo definido pelo usuário é definido em um namespace.</span><span class="sxs-lookup"><span data-stu-id="9075e-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="9075e-131">O Q # segue as mesmas regras para nomear como outras linguagens .NET.</span><span class="sxs-lookup"><span data-stu-id="9075e-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="9075e-132">No entanto, Q # não oferece suporte a referências relativas a namespaces.</span><span class="sxs-lookup"><span data-stu-id="9075e-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="9075e-133">Ou seja, se o namespace `a.b` tiver sido aberto, uma referência a uma operação de nomes `c.d` não será resolvida para uma operação com o nome completo `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="9075e-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="9075e-134">Dentro de um bloco de namespace, a diretiva `open` pode ser usada para importar todos os tipos e chamadores declarados em um determinado namespace e consultá-los por seu nome não qualificado.</span><span class="sxs-lookup"><span data-stu-id="9075e-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="9075e-135">Opcionalmente, um nome curto para o namespace aberto pode ser definido de modo que todos os elementos desse namespace possam (e precisam) ser qualificados pelo nome curto definido.</span><span class="sxs-lookup"><span data-stu-id="9075e-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="9075e-136">A diretiva `open` se aplica ao bloco de namespace inteiro em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="9075e-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="9075e-137">Um tipo ou callable definido em outro namespace que não está aberto no namespace atual deve ser referenciado por seu nome totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="9075e-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="9075e-138">Por exemplo, uma operação chamada `Op` no namespace `X.Y` deve ser referenciada por seu nome totalmente qualificado `X.Y.Op`, a menos que o namespace `X.Y` tenha sido aberto anteriormente no bloco atual.</span><span class="sxs-lookup"><span data-stu-id="9075e-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="9075e-139">Conforme mencionado acima, mesmo que o namespace de `X` tenha sido aberto, não é possível fazer referência à operação como `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="9075e-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="9075e-140">Se um nome curto `Z` para `X.Y` tiver sido definido nesse namespace e arquivo, `Op` precisará ser chamado de `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="9075e-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="9075e-141">Geralmente, é melhor incluir um namespace usando uma diretiva `open`.</span><span class="sxs-lookup"><span data-stu-id="9075e-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="9075e-142">Usar um nome totalmente qualificado é necessário se dois namespaces definem construções com o mesmo nome e a fonte atual usa construções de ambos.</span><span class="sxs-lookup"><span data-stu-id="9075e-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="9075e-143">Formatação</span><span class="sxs-lookup"><span data-stu-id="9075e-143">Formatting</span></span>

<span data-ttu-id="9075e-144">A maioria das instruções Q # e diretivas terminam com um ponto e vírgula de terminação, `;`.</span><span class="sxs-lookup"><span data-stu-id="9075e-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="9075e-145">Instruções e declarações como `for` e `operation` que terminam com um bloco de instruções não exigem um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="9075e-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="9075e-146">Cada descrição de instrução observa se o ponto e vírgula de terminação é necessário.</span><span class="sxs-lookup"><span data-stu-id="9075e-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="9075e-147">Instruções, como expressões, declarações e diretivas, podem ser divididas em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="9075e-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="9075e-148">Ter várias instruções em uma única linha deve ser evitada.</span><span class="sxs-lookup"><span data-stu-id="9075e-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="9075e-149">Blocos de instrução</span><span class="sxs-lookup"><span data-stu-id="9075e-149">Statement Blocks</span></span>

<span data-ttu-id="9075e-150">As instruções Q # são agrupadas em blocos de instrução.</span><span class="sxs-lookup"><span data-stu-id="9075e-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="9075e-151">Um bloco de instruções começa com um `{` de abertura e termina com um `}`de fechamento.</span><span class="sxs-lookup"><span data-stu-id="9075e-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="9075e-152">Um bloco de instrução que está delimitado de forma lexical dentro de outro bloco é considerado um subbloco do bloco de contenção; os blocos e os subcontêineres também são chamados de bloco externo e interno.</span><span class="sxs-lookup"><span data-stu-id="9075e-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="9075e-153">Atribuição e Associação de símbolo</span><span class="sxs-lookup"><span data-stu-id="9075e-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="9075e-154">Q # distingue entre símbolos mutáveis e imutáveis.</span><span class="sxs-lookup"><span data-stu-id="9075e-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="9075e-155">Em geral, o uso de símbolos imutáveis é incentivado porque permite que o compilador execute mais otimizações.</span><span class="sxs-lookup"><span data-stu-id="9075e-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="9075e-156">O lado esquerdo da Associação consiste em uma tupla de símbolos e no lado direito de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="9075e-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="9075e-157">Como todos os tipos de Q # são tipos de valor – com o qubits de uma função especial, formalmente uma "cópia" é criada quando um valor é associado a um símbolo ou quando um símbolo é reassociado.</span><span class="sxs-lookup"><span data-stu-id="9075e-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="9075e-158">Isso significa que o comportamento de Q # é o mesmo que se uma cópia fosse criada na atribuição.</span><span class="sxs-lookup"><span data-stu-id="9075e-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="9075e-159">Isso, em particular, também inclui matrizes.</span><span class="sxs-lookup"><span data-stu-id="9075e-159">This in particular also includes arrays.</span></span> <span data-ttu-id="9075e-160">É claro que, na prática, apenas as partes relevantes são, na verdade, recriadas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9075e-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="9075e-161">Desconstrução de tupla</span><span class="sxs-lookup"><span data-stu-id="9075e-161">Tuple Deconstruction</span></span>

<span data-ttu-id="9075e-162">Se o lado direito da associação for uma tupla, essa tupla poderá ser desconstruída após a atribuição.</span><span class="sxs-lookup"><span data-stu-id="9075e-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="9075e-163">Essas desconstruções podem envolver tuplas aninhadas e qualquer desconstrução completa ou parcial é válida, desde que a forma da tupla no lado direito seja compatível com a forma da tupla de símbolo.</span><span class="sxs-lookup"><span data-stu-id="9075e-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="9075e-164">A desconstrução de tupla pode, em particular, também ser usada quando o lado direito da `=` é uma expressão com valor de tupla.</span><span class="sxs-lookup"><span data-stu-id="9075e-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="9075e-165">Símbolos imutáveis</span><span class="sxs-lookup"><span data-stu-id="9075e-165">Immutable Symbols</span></span>

<span data-ttu-id="9075e-166">Os símbolos imutáveis são associados usando a instrução `let`.</span><span class="sxs-lookup"><span data-stu-id="9075e-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="9075e-167">Isso é praticamente equivalente à declaração de variável e à inicialização em idiomas C#como, exceto que os símbolos Q #, uma vez vinculados, não podem ser alterados; associações de `let` são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="9075e-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="9075e-168">Uma associação imutável consiste na palavra-chave `let`, seguida por uma tupla de símbolo ou símbolo, um sinal de igual `=`, uma expressão para associar os símbolos a e um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="9075e-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="9075e-169">O tipo de símbolo (s) associado é inferido com base na expressão no lado direito.</span><span class="sxs-lookup"><span data-stu-id="9075e-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="9075e-170">Símbolos mutáveis</span><span class="sxs-lookup"><span data-stu-id="9075e-170">Mutable Symbols</span></span>

<span data-ttu-id="9075e-171">Os símbolos mutáveis são definidos e inicializados usando a instrução `mutable`.</span><span class="sxs-lookup"><span data-stu-id="9075e-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="9075e-172">Os símbolos declarados e associados como parte de uma instrução `mutable` podem ser reassociados a um valor diferente posteriormente no código.</span><span class="sxs-lookup"><span data-stu-id="9075e-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="9075e-173">Uma instrução de associação mutável consiste na palavra-chave `mutable`, seguida por uma tupla de símbolo ou símbolo, um sinal de igual `=`, uma expressão para associar os símbolos a e um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="9075e-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="9075e-174">O tipo de símbolo (s) associado é inferido com base na expressão no lado direito.</span><span class="sxs-lookup"><span data-stu-id="9075e-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="9075e-175">Se um símbolo for reassociado posteriormente no código, seu tipo não será alterado e o valor de limite precisará ser compatível com esse tipo.</span><span class="sxs-lookup"><span data-stu-id="9075e-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="9075e-176">Reassociação de símbolos mutáveis</span><span class="sxs-lookup"><span data-stu-id="9075e-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="9075e-177">Uma variável mutável pode ser reassociada usando uma instrução `set`.</span><span class="sxs-lookup"><span data-stu-id="9075e-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="9075e-178">Essa reassociação consiste na `set`da palavra-chave, seguida por uma tupla de símbolo ou símbolo, um sinal de igual `=`, uma expressão para reassociar os símbolos a e um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="9075e-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="9075e-179">O valor deve ser compatível com os tipos do (s) símbolo (es) ao qual está associado.</span><span class="sxs-lookup"><span data-stu-id="9075e-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="9075e-180">Instrução de aplicação e reatribuição</span><span class="sxs-lookup"><span data-stu-id="9075e-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="9075e-181">Um tipo específico de instrução SET-Statement que chamamos de instrução de aplicação e reatribuição fornece uma maneira conveniente de concatenação se o lado direito consistir no aplicativo de um operador binário e o resultado for ser reassociado ao argumento esquerdo para o operador.</span><span class="sxs-lookup"><span data-stu-id="9075e-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="9075e-182">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="9075e-183">incrementa o valor do contador `counter` em cada iteração do loop `for`.</span><span class="sxs-lookup"><span data-stu-id="9075e-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="9075e-184">O código acima é equivalente a</span><span class="sxs-lookup"><span data-stu-id="9075e-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="9075e-185">Instruções semelhantes estão disponíveis para todos os operadores binários nos quais o tipo do lado esquerdo corresponde ao tipo de expressão.</span><span class="sxs-lookup"><span data-stu-id="9075e-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="9075e-186">Isso fornece, por exemplo, uma maneira conveniente de acumular valores:</span><span class="sxs-lookup"><span data-stu-id="9075e-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="9075e-187">Instrução UPDATE-and-REASSIGN</span><span class="sxs-lookup"><span data-stu-id="9075e-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="9075e-188">Existe uma concatenação semelhante para expressões de copiar e atualizar no lado direito.</span><span class="sxs-lookup"><span data-stu-id="9075e-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="9075e-189">De modo correspondente, as instruções UPDATE-and-REASSIGN existem para itens nomeados em tipos definidos pelo usuário, bem como para itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="9075e-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
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

<span data-ttu-id="9075e-190">No caso de matrizes, nossas bibliotecas padrão contêm as ferramentas necessárias para muitas necessidades comuns de inicialização e manipulação de matriz e, portanto, ajudam a evitar a necessidade de atualizar itens de matriz em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="9075e-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="9075e-191">As instruções UPDATE-and-REASSIGN fornecem uma alternativa, se necessário:</span><span class="sxs-lookup"><span data-stu-id="9075e-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="9075e-192">Evite o uso desnecessário de instruções UPDATE-and-REASSIGN aproveitando as ferramentas fornecidas no <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="9075e-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="9075e-193">A função</span><span class="sxs-lookup"><span data-stu-id="9075e-193">The function</span></span>
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="9075e-194">por exemplo, pode simplesmente ser simplificado usando a função `ConstantArray` em `Microsoft.Quantum.Arrays`e retornar uma expressão de copiar e atualizar:</span><span class="sxs-lookup"><span data-stu-id="9075e-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="9075e-195">Escopos de associação</span><span class="sxs-lookup"><span data-stu-id="9075e-195">Binding Scopes</span></span>

<span data-ttu-id="9075e-196">Em geral, as ligações de símbolo saem do escopo e se tornam inoperantes no final do bloco de instrução em que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="9075e-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="9075e-197">Há duas exceções a essa regra:</span><span class="sxs-lookup"><span data-stu-id="9075e-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="9075e-198">A associação da variável de loop de um loop de `for` está no escopo do corpo do loop for, mas não após o final do loop.</span><span class="sxs-lookup"><span data-stu-id="9075e-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="9075e-199">Todas as três partes de um `repeat`/loop de `until` (o corpo, o teste e a correção) são tratados como um único escopo, de modo que os símbolos associados ao corpo estão disponíveis no teste e no conserto.</span><span class="sxs-lookup"><span data-stu-id="9075e-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="9075e-200">Para ambos os tipos de loops, cada passagem do loop é executada em seu próprio escopo, portanto, as associações de uma passagem anterior não estarão disponíveis em uma passagem posterior.</span><span class="sxs-lookup"><span data-stu-id="9075e-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="9075e-201">Associações de símbolo de blocos externos são herdadas por blocos internos.</span><span class="sxs-lookup"><span data-stu-id="9075e-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="9075e-202">Um símbolo só pode ser associado uma vez por bloco; é ilegal definir um símbolo com o mesmo nome de outro símbolo que está dentro do escopo (sem "sombreamento").</span><span class="sxs-lookup"><span data-stu-id="9075e-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="9075e-203">As sequências a seguir seriam legais:</span><span class="sxs-lookup"><span data-stu-id="9075e-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="9075e-204">e em</span><span class="sxs-lookup"><span data-stu-id="9075e-204">and</span></span>

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
```

<span data-ttu-id="9075e-205">Mas isso seria ilegal:</span><span class="sxs-lookup"><span data-stu-id="9075e-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="9075e-206">como seria:</span><span class="sxs-lookup"><span data-stu-id="9075e-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="9075e-207">Fluxo de Controlo</span><span class="sxs-lookup"><span data-stu-id="9075e-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="9075e-208">Loop for</span><span class="sxs-lookup"><span data-stu-id="9075e-208">For Loop</span></span>

<span data-ttu-id="9075e-209">A instrução `for` dá suporte à iteração em um intervalo de inteiros ou em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="9075e-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="9075e-210">A instrução consiste na palavra-chave `for`, um parêntese de abertura `(`, seguido por uma tupla de símbolo ou símbolo, a palavra-chave `in`, uma expressão do tipo `Range` ou matriz, um parêntese de fechamento `)`e um bloco de instruções.</span><span class="sxs-lookup"><span data-stu-id="9075e-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="9075e-211">O bloco de instrução (o corpo do loop) é executado repetidamente, com os símbolos definidos (as variáveis de loop) associadas a cada valor no intervalo ou na matriz.</span><span class="sxs-lookup"><span data-stu-id="9075e-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="9075e-212">Observe que, se a expressão de intervalo for avaliada como um intervalo ou uma matriz vazia, o corpo não será executado.</span><span class="sxs-lookup"><span data-stu-id="9075e-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="9075e-213">A expressão é totalmente avaliada antes de entrar no loop e não será alterada enquanto o loop estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="9075e-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="9075e-214">A Associação dos símbolos declarados é imutável e segue as mesmas regras que outras associações de variáveis.</span><span class="sxs-lookup"><span data-stu-id="9075e-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="9075e-215">Em particular, é possível destruir, por exemplo, itens de matriz para uma iteração em uma matriz após a atribuição à (s) variável (ões) de loop.</span><span class="sxs-lookup"><span data-stu-id="9075e-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="9075e-216">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-216">For example,</span></span>

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="9075e-217">A variável de loop é associada a cada entrada no corpo do loop e desassociada no final do corpo.</span><span class="sxs-lookup"><span data-stu-id="9075e-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="9075e-218">Em particular, a variável de loop não é associada depois que o loop for é concluído.</span><span class="sxs-lookup"><span data-stu-id="9075e-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="9075e-219">Repetir-loop Until-êxito</span><span class="sxs-lookup"><span data-stu-id="9075e-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="9075e-220">A instrução `repeat` dá suporte ao padrão Quantum "repetir até o sucesso".</span><span class="sxs-lookup"><span data-stu-id="9075e-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="9075e-221">Ele consiste na palavra-chave `repeat`, seguida por um bloco de instrução (o corpo do _loop_ ), a palavra-chave `until`, uma expressão booleana e um ponto e vírgula de terminação ou a palavra-chave `fixup` seguido por outro bloco de instrução (a _correção_).</span><span class="sxs-lookup"><span data-stu-id="9075e-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="9075e-222">O corpo, a condição e a correção do loop são considerados um único escopo, portanto, os símbolos associados ao corpo estão disponíveis na condição e na correção.</span><span class="sxs-lookup"><span data-stu-id="9075e-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

<span data-ttu-id="9075e-223">O corpo do loop é executado e a condição é avaliada.</span><span class="sxs-lookup"><span data-stu-id="9075e-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="9075e-224">Se a condição for verdadeira, a instrução será concluída; caso contrário, a correção será executada e a instrução será executada novamente começando com o corpo do loop.</span><span class="sxs-lookup"><span data-stu-id="9075e-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="9075e-225">Observe que a conclusão da execução da correção encerra o escopo da instrução, para que as associações de símbolo feitas durante o corpo ou correção não estejam disponíveis em repetições subsequentes.</span><span class="sxs-lookup"><span data-stu-id="9075e-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="9075e-226">Por exemplo, o código a seguir é um circuito probabilística que implementa um portão de rotação importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ usando o Hadamard e T Gates.</span><span class="sxs-lookup"><span data-stu-id="9075e-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="9075e-227">O loop termina em 8/5 repetições em média.</span><span class="sxs-lookup"><span data-stu-id="9075e-227">The loop terminates in 8/5 repetitions on average.</span></span>
<span data-ttu-id="9075e-228">Consulte [*repetir-até-êxito: decomposição não determinística de unidades de qubit único*](https://arxiv.org/abs/1311.1074) (Paetznick e Svore, 2014) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="9075e-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> <span data-ttu-id="9075e-229">Evite usar loops repetir-até-sucesso dentro de funções.</span><span class="sxs-lookup"><span data-stu-id="9075e-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="9075e-230">A funcionalidade correspondente é fornecida por loops em funções do.</span><span class="sxs-lookup"><span data-stu-id="9075e-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="9075e-231">Loop while</span><span class="sxs-lookup"><span data-stu-id="9075e-231">While Loop</span></span>

<span data-ttu-id="9075e-232">Os padrões de repetição-até-sucesso têm uma connotação de muito Quantum específica.</span><span class="sxs-lookup"><span data-stu-id="9075e-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="9075e-233">Eles são amplamente usados em classes específicas de algoritmos Quantum, portanto, a construção de linguagem dedicada em Q #.</span><span class="sxs-lookup"><span data-stu-id="9075e-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="9075e-234">No entanto, os loops que quebram com base em uma condição e cujo comprimento de execução é, portanto, desconhecido em tempo de compilação precisam ser manipulados com cuidado específico em um tempo de execução do Quantum.</span><span class="sxs-lookup"><span data-stu-id="9075e-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="9075e-235">Seu uso dentro de funções por outro lado é inproblemático, pois elas contêm apenas o código que será executado em hardware convencional (sem Quantum).</span><span class="sxs-lookup"><span data-stu-id="9075e-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="9075e-236">O Q #, portanto, dá suporte ao uso de loops while apenas dentro de funções.</span><span class="sxs-lookup"><span data-stu-id="9075e-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="9075e-237">Uma instrução `while` consiste na `while`de palavras-chave, uma `(`de parênteses aberto, uma condição (ou seja, uma expressão booleana), um parêntese de fechamento `)`e um bloco de instruções.</span><span class="sxs-lookup"><span data-stu-id="9075e-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="9075e-238">O bloco de instrução (o corpo do loop) é executado contanto que a condição seja avaliada como `true`.</span><span class="sxs-lookup"><span data-stu-id="9075e-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="9075e-239">Instrução condicional</span><span class="sxs-lookup"><span data-stu-id="9075e-239">Conditional Statement</span></span>

<span data-ttu-id="9075e-240">A instrução `if` dá suporte à execução condicional.</span><span class="sxs-lookup"><span data-stu-id="9075e-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="9075e-241">Ele consiste na palavra-chave `if`, um `(`de parênteses aberto, uma expressão booleana, um parêntese de fechamento `)`e um bloco de instruções (o bloco _then_ ).</span><span class="sxs-lookup"><span data-stu-id="9075e-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="9075e-242">Isso pode ser seguido por qualquer número de cláusulas else-if, cada uma das quais consiste na palavra-chave `elif`, um parênteses de abertura `(`, uma expressão booleana, um parêntese de fechamento `)`e um bloco de instrução (o bloco _else-if_ ).</span><span class="sxs-lookup"><span data-stu-id="9075e-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="9075e-243">Por fim, a instrução pode, opcionalmente, ser concluída com uma cláusula else, que consiste na palavra-chave `else` seguida por outro bloco de instrução (o bloco _else_ ).</span><span class="sxs-lookup"><span data-stu-id="9075e-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="9075e-244">A condição é avaliada e, se for verdadeira, o bloco then será executado.</span><span class="sxs-lookup"><span data-stu-id="9075e-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="9075e-245">Se a condição for falsa, a primeira condição IF-IF será avaliada; Se for true, o bloco else if será executado.</span><span class="sxs-lookup"><span data-stu-id="9075e-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="9075e-246">Caso contrário, o segundo bloco else é testado e, em seguida, o terceiro, e assim por diante, até que seja encontrada uma cláusula com uma condição true ou que não haja mais cláusulas If-If.</span><span class="sxs-lookup"><span data-stu-id="9075e-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="9075e-247">Se a condição if original e todas as cláusulas If forem avaliadas como false, o bloco else será executado se um for fornecido.</span><span class="sxs-lookup"><span data-stu-id="9075e-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="9075e-248">Observe que qualquer bloco executado é executado em seu próprio escopo.</span><span class="sxs-lookup"><span data-stu-id="9075e-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="9075e-249">Associações feitas dentro de um bloco then, else-if ou else não são visíveis após o final da instrução If.</span><span class="sxs-lookup"><span data-stu-id="9075e-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="9075e-250">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="9075e-251">ou</span><span class="sxs-lookup"><span data-stu-id="9075e-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="9075e-252">exibir</span><span class="sxs-lookup"><span data-stu-id="9075e-252">Return</span></span>

<span data-ttu-id="9075e-253">A instrução return encerra a execução de uma operação ou função e retorna um valor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="9075e-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="9075e-254">Ele consiste na palavra-chave `return`, seguida por uma expressão do tipo apropriado e um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="9075e-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="9075e-255">Um callable que retorna uma tupla vazia, `()`, não requer uma instrução de retorno.</span><span class="sxs-lookup"><span data-stu-id="9075e-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="9075e-256">Se uma saída antecipada for desejada, `return ()` poderá ser usada nesse caso.</span><span class="sxs-lookup"><span data-stu-id="9075e-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="9075e-257">Os chamadores que retornam qualquer outro tipo exigem uma instrução de retorno final.</span><span class="sxs-lookup"><span data-stu-id="9075e-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="9075e-258">Não há um número máximo de instruções de retorno em uma operação.</span><span class="sxs-lookup"><span data-stu-id="9075e-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="9075e-259">O compilador pode emitir um aviso se as instruções seguirem uma instrução return dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="9075e-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="9075e-260">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="9075e-261">ou</span><span class="sxs-lookup"><span data-stu-id="9075e-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="9075e-262">ou</span><span class="sxs-lookup"><span data-stu-id="9075e-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="9075e-263">Recuperação</span><span class="sxs-lookup"><span data-stu-id="9075e-263">Fail</span></span>

<span data-ttu-id="9075e-264">A instrução Fail encerra a execução de uma operação e retorna um valor de erro para o chamador.</span><span class="sxs-lookup"><span data-stu-id="9075e-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="9075e-265">Ela consiste na `fail`de palavras-chave, seguida por uma cadeia de caracteres e um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="9075e-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="9075e-266">A cadeia de caracteres é retornada ao driver clássico como a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="9075e-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="9075e-267">Não há nenhuma restrição quanto ao número de instruções de falha em uma operação.</span><span class="sxs-lookup"><span data-stu-id="9075e-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="9075e-268">O compilador pode emitir um aviso se as instruções seguirem uma instrução Fail dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="9075e-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="9075e-269">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="9075e-270">ou</span><span class="sxs-lookup"><span data-stu-id="9075e-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="9075e-271">Gerenciamento de qubit</span><span class="sxs-lookup"><span data-stu-id="9075e-271">Qubit Management</span></span>

<span data-ttu-id="9075e-272">Observe que nenhuma dessas instruções é permitida dentro do corpo de uma função.</span><span class="sxs-lookup"><span data-stu-id="9075e-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="9075e-273">Eles só são válidos dentro de operações.</span><span class="sxs-lookup"><span data-stu-id="9075e-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="9075e-274">Limpar qubits</span><span class="sxs-lookup"><span data-stu-id="9075e-274">Clean Qubits</span></span>

<span data-ttu-id="9075e-275">A instrução `using` é usada para adquirir novas qubits para uso durante um bloco de instruções.</span><span class="sxs-lookup"><span data-stu-id="9075e-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="9075e-276">Os qubits têm a garantia de serem inicializados para o estado computacional `Zero`.</span><span class="sxs-lookup"><span data-stu-id="9075e-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="9075e-277">O qubits deve estar no estado computacional `Zero` no final do bloco de instrução; os simuladores são incentivados a impor isso.</span><span class="sxs-lookup"><span data-stu-id="9075e-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="9075e-278">A instrução consiste na `using`de palavras-chave, seguida por um parêntese de abertura `(`, uma associação, um parêntese de fechamento `)`e o bloco de instruções dentro do qual o qubits estará disponível.</span><span class="sxs-lookup"><span data-stu-id="9075e-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="9075e-279">A associação segue o mesmo padrão que `let` instruções: um único símbolo ou uma tupla de símbolos, seguido por um sinal de igual `=`e um único valor ou uma tupla correspondente de inicializadores.</span><span class="sxs-lookup"><span data-stu-id="9075e-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="9075e-280">Inicializadores estão disponíveis para um único qubit, indicado como `Qubit()`, ou uma matriz de qubits, indicada por `Qubit[`, uma expressão de `Int` e `]`.</span><span class="sxs-lookup"><span data-stu-id="9075e-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="9075e-281">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-281">For example,</span></span>

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a><span data-ttu-id="9075e-282">Qubits sujos</span><span class="sxs-lookup"><span data-stu-id="9075e-282">Dirty Qubits</span></span>

<span data-ttu-id="9075e-283">A instrução `borrowing` é usada para obter qubits para uso temporário.</span><span class="sxs-lookup"><span data-stu-id="9075e-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="9075e-284">A instrução consiste na `borrowing`de palavras-chave, seguida por um parêntese de abertura `(`, uma associação, um parêntese de fechamento `)`e o bloco de instruções dentro do qual o qubits estará disponível.</span><span class="sxs-lookup"><span data-stu-id="9075e-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="9075e-285">A associação segue o mesmo padrão e regras que uma em uma instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="9075e-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="9075e-286">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-286">For example,</span></span>

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="9075e-287">O qubits emprestado está em um estado desconhecido e sai do escopo no final do bloco de instrução.</span><span class="sxs-lookup"><span data-stu-id="9075e-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="9075e-288">O tomador de confirmações para deixar o qubits no mesmo estado em que estavam emprestados, ou seja, seu estado no início e no final do bloco de instrução deve ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="9075e-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="9075e-289">Esse estado em particular não é necessariamente um estado clássico, de modo que, na maioria dos casos, os escopos emprestados não devem conter medidas.</span><span class="sxs-lookup"><span data-stu-id="9075e-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="9075e-290">Esses qubits geralmente são conhecidos como "Dirty ancilla".</span><span class="sxs-lookup"><span data-stu-id="9075e-290">Such qubits are often known as “dirty ancilla”.</span></span>
<span data-ttu-id="9075e-291">Consulte [*fatoração usando 2n + 2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) para obter um exemplo de uso de ancilla sujos.</span><span class="sxs-lookup"><span data-stu-id="9075e-291">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of dirty ancilla use.</span></span>

<span data-ttu-id="9075e-292">Ao emprestar qubits, o sistema primeiro tentará preencher a solicitação de qubits que estão em uso, mas que não são acessadas durante o corpo da instrução `borrowing`.</span><span class="sxs-lookup"><span data-stu-id="9075e-292">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="9075e-293">Se não houver tal qubits suficiente, ele alocará o novo qubits para concluir a solicitação.</span><span class="sxs-lookup"><span data-stu-id="9075e-293">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="9075e-294">Conjugações</span><span class="sxs-lookup"><span data-stu-id="9075e-294">Conjugations</span></span>

<span data-ttu-id="9075e-295">Em contraste com os bits clássicos, liberar memória Quantum é um pouco mais envolvida, uma vez que a redefinição oculta de qubits pode ter efeitos indesejados na computação restante se o qubits ainda for confusas.</span><span class="sxs-lookup"><span data-stu-id="9075e-295">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="9075e-296">Isso pode ser evitado com o "desfazendo" adequadamente os cálculos executados antes de liberar a memória.</span><span class="sxs-lookup"><span data-stu-id="9075e-296">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="9075e-297">Um padrão comum na computação Quantum é, portanto, o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9075e-297">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="9075e-298">: novo: começando com nossa versão 0,9, damos suporte a uma instrução Conjugation que implementa a transformação acima.</span><span class="sxs-lookup"><span data-stu-id="9075e-298">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="9075e-299">Usando essa instrução, a operação `ApplyWith` pode ser implementada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9075e-299">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="9075e-300">Uma instrução de conjugação, obviamente, se torna muito mais útil se as transformações externa e interna não estão prontamente disponíveis como operações, mas são mais convenientes de descrever por um bloco que consiste em várias instruções.</span><span class="sxs-lookup"><span data-stu-id="9075e-300">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="9075e-301">A transformação inversa para as instruções definidas no bloco Within é gerada automaticamente pelo compilador e executada após a conclusão do bloco de aplicação.</span><span class="sxs-lookup"><span data-stu-id="9075e-301">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="9075e-302">Como as variáveis mutáveis usadas como parte do bloco Within não podem ser reassociadas no bloco Apply, a transformação gerada é garantida como sendo a adjoin do cálculo no bloco Within.</span><span class="sxs-lookup"><span data-stu-id="9075e-302">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="9075e-303">Instruções de avaliação de expressão</span><span class="sxs-lookup"><span data-stu-id="9075e-303">Expression Evaluation Statements</span></span>

<span data-ttu-id="9075e-304">Qualquer expressão de chamada do tipo `Unit` pode ser usada como uma instrução.</span><span class="sxs-lookup"><span data-stu-id="9075e-304">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="9075e-305">Isso é basicamente usado ao chamar operações em qubits que retornam `Unit` porque a finalidade da instrução é modificar o estado de Quantum implícito.</span><span class="sxs-lookup"><span data-stu-id="9075e-305">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="9075e-306">As instruções de avaliação de expressão exigem um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="9075e-306">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="9075e-307">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9075e-307">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
