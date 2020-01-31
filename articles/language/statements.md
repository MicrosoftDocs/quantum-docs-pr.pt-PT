---
title: Q# declarações / Microsoft Docs
description: Q# declarações
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9157cf3336ce0894816dbfbaf13ce0e712a6b096
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821070"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="ddfa9-103">Declarações e Outras Construções</span><span class="sxs-lookup"><span data-stu-id="ddfa9-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="ddfa9-104">Comentários</span><span class="sxs-lookup"><span data-stu-id="ddfa9-104">Comments</span></span>

<span data-ttu-id="ddfa9-105">Os comentários começam com dois cortes dianteiros, `//`, e continuam até ao fim da linha.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="ddfa9-106">Um comentário pode aparecer em qualquer lugar num ficheiro de origem Q#.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="ddfa9-107">Comentários de Documentação</span><span class="sxs-lookup"><span data-stu-id="ddfa9-107">Documentation Comments</span></span>

<span data-ttu-id="ddfa9-108">Os comentários que começam com três cortes dianteiros, `///`, são tratados especialmente pelo compilador quando aparecem imediatamente antes de um espaço de nome, operação, especialização, função ou definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="ddfa9-109">Nesse caso, os seus conteúdos são tomados como documentação para o tipo definido de callable ou definido pelo utilizador, como para outros idiomas .NET.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="ddfa9-110">No `///` comentários, o texto a aparecer como parte da documentação da API é formatado como [Markdown](https://daringfireball.net/projects/markdown/syntax), com diferentes partes da documentação a serem indicadas por cabeçalhos especialmente nomeados.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="ddfa9-111">Como extensão ao Markdown, as referências cruzadas a operações, funções e tipos definidos pelo utilizador em Q# podem ser incluídas utilizando o `@"<ref target>"`, onde `<ref target>` é substituído pelo nome totalmente qualificado do objeto de código que está a ser referenciado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="ddfa9-112">Opcionalmente, um motor de documentação também pode suportar extensões de Markdown adicionais.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="ddfa9-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-113">For example:</span></span>

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="ddfa9-114">Os seguintes nomes são reconhecidos como cabeçalhos de comentário documentais.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="ddfa9-115">**Resumo**: Um resumo curto do comportamento de uma função ou operação, ou do propósito de um tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="ddfa9-116">O primeiro parágrafo do resumo é utilizado para informações sobre pairar.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="ddfa9-117">Deve ser um texto simples.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-117">It should be plain text.</span></span>
- <span data-ttu-id="ddfa9-118">**Descrição**: Uma descrição do comportamento de uma função ou operação, ou do propósito de um tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="ddfa9-119">O resumo e a descrição são concatenados para formar o ficheiro de documentação gerado para a função, operação ou tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="ddfa9-120">A descrição pode conter símbolos e equações formatados em linha LaTeX.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="ddfa9-121">**Entrada**: Uma descrição do tuple de entrada para uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="ddfa9-122">Pode conter subsecções de Markdown adicionais indicando cada elemento individual da tuple de entrada.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="ddfa9-123">**Saída**: Uma descrição do tuple devolvido por uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="ddfa9-124">**Parâmetros do tipo**: Uma secção vazia que contém uma subsecção adicional para cada parâmetro genérico do tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="ddfa9-125">**Exemplo**: Um pequeno exemplo do funcionamento, função ou tipo de utilização.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="ddfa9-126">**Observações**: Prosa diversa que descreve algum aspeto da operação, função ou tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="ddfa9-127">**Ver Também:** Uma lista de nomes totalmente qualificados que indicam funções, operações ou tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="ddfa9-128">**Referências**: Uma lista de referências e citações para o artigo que está a ser documentado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="ddfa9-129">Espaços de nomes</span><span class="sxs-lookup"><span data-stu-id="ddfa9-129">Namespaces</span></span>

<span data-ttu-id="ddfa9-130">Cada operação, função e tipo definido pelo utilizador é definido dentro de um espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="ddfa9-131">Q# segue as mesmas regras para nomear outras línguas .NET.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="ddfa9-132">No entanto, Q# não suporta referências relativas a espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="ddfa9-133">Ou seja, se o espaço de nome`a.b` tiver sido aberto, uma referência a uma operação nomea `c.d` não será resolvida a uma operação com o nome completo `a.b.c.d`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="ddfa9-134">Dentro de um bloco de espaço-nome, a diretiva `open` pode ser utilizada para importar todos os tipos e calíveis declarados num determinado espaço de nome e encaminhá-los pelo seu nome não qualificado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="ddfa9-135">Opcionalmente, pode ser definido um nome curto para o espaço de nome aberto de modo a que todos os elementos desse espaço de nome possam (e precisam) ser qualificados pelo nome curto definido.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="ddfa9-136">A diretiva `open` aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="ddfa9-137">Um tipo ou callable definido em outro espaço de nome que não esteja aberto no espaço de nome atual deve ser referenciado pelo seu nome totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="ddfa9-138">Por exemplo, uma operação denominada `Op` no espaço de nome `X.Y` deve ser referenciada pelo seu nome totalmente qualificado `X.Y.Op`, a menos que o espaço de nome `X.Y` tenha sido aberto mais cedo no bloco atual.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="ddfa9-139">Como mencionado acima, mesmo que tenha sido aberto o espaço de nome `X`, não é possível fazer referência à operação como `Y.Op`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="ddfa9-140">Se um nome curto `Z` para `X.Y` tiver sido definido nesse espaço de nome e arquivo, então `Op` deve ser referido como `Z.Op`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="ddfa9-141">Normalmente, é melhor incluir um espaço de nome através de uma diretiva `open`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="ddfa9-142">É necessário utilizar um nome totalmente qualificado se dois espaços de nome definirem construções com o mesmo nome, e a fonte atual utiliza construções de ambos.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="ddfa9-143">Formatação</span><span class="sxs-lookup"><span data-stu-id="ddfa9-143">Formatting</span></span>

<span data-ttu-id="ddfa9-144">A maioria das declarações e diretivas q# terminam com um ponto evígula terminando, `;`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="ddfa9-145">Declarações e declarações como `for` e `operation` que terminam com um bloco de declaração não requerem um ponto e vírgula terminando.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="ddfa9-146">Cada descrição da declaração observa se o ponto evículo terminando é necessário.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="ddfa9-147">Declarações, como expressões, declarações e diretivas, podem ser quebradas em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="ddfa9-148">Deve evitar-se várias declarações numa única linha.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="ddfa9-149">Blocos de Declaração</span><span class="sxs-lookup"><span data-stu-id="ddfa9-149">Statement Blocks</span></span>

<span data-ttu-id="ddfa9-150">As declarações de Q# são agruparadas em blocos de declaração.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="ddfa9-151">Um bloco de declaração começa com uma abertura `{` e termina com um fecho `}`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="ddfa9-152">Um bloco de declaração que seja lexicamente fechado dentro de outro bloco é considerado um subbloco do bloco contendo; contendo e subblocos também são chamados blocos exteriores e internos.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="ddfa9-153">Ligação e atribuição de símbolos</span><span class="sxs-lookup"><span data-stu-id="ddfa9-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="ddfa9-154">Q# distingue entre símbolos mutáveis e imutáveis.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="ddfa9-155">Em geral, o uso de símbolos imutáveis é encorajado porque permite ao compilador realizar mais otimizações.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="ddfa9-156">O lado esquerdo da ligação consiste num símbolo tuple, e no lado direito de uma expressão.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="ddfa9-157">Uma vez que todos os tipos de Q# são tipos de valor - com os qubits a assumirem um papel um pouco especial - formalmente é criada uma "cópia" quando um valor está ligado a um símbolo, ou quando um símbolo é recuperado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="ddfa9-158">Ou seja, o comportamento do Q# é o mesmo que se uma cópia fosse criada na atribuição.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="ddfa9-159">Isto, em particular, também inclui matrizes.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-159">This in particular also includes arrays.</span></span> <span data-ttu-id="ddfa9-160">É claro que, na prática, apenas as peças relevantes são recriadas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="ddfa9-161">Desconstrução de Tuple</span><span class="sxs-lookup"><span data-stu-id="ddfa9-161">Tuple Deconstruction</span></span>

<span data-ttu-id="ddfa9-162">Se o lado direito da ligação for uma tuple, então essa tuple pode ser desconstruída após a atribuição.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="ddfa9-163">Tais desconstruções podem envolver tuples aninhados, e qualquer desconstrução total ou parcial é válida desde que a forma da tuple no lado direito seja compatível com a forma do símbolo tuple.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="ddfa9-164">A desconstrução de Tuple pode, em particular, ser usada quando o lado direito do `=` é uma expressão de valor tuple.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="ddfa9-165">Símbolos imutáveis</span><span class="sxs-lookup"><span data-stu-id="ddfa9-165">Immutable Symbols</span></span>

<span data-ttu-id="ddfa9-166">Os símbolos imutáveis são ligados usando a declaração `let`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="ddfa9-167">Isto equivale aproximadamente à declaração variável e C#à inicialização em línguas como, exceto que os símbolos Q#, uma vez ligados, não podem ser alterados; `let` encadernações são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="ddfa9-168">Uma ligação imutável consiste na palavra-chave `let`, seguida de um símbolo ou túnica de símbolo, um sinal igual `=`, uma expressão para ligar o símbolo(s) a, e um ponto evícito terminando.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="ddfa9-169">O tipo de símbolo s de atado é inferido com base na expressão do lado direito.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="ddfa9-170">Símbolos mutáveis</span><span class="sxs-lookup"><span data-stu-id="ddfa9-170">Mutable Symbols</span></span>

<span data-ttu-id="ddfa9-171">Os símbolos mutáveis são definidos e inicializados utilizando a declaração `mutable`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="ddfa9-172">Os símbolos declarados e vinculados como parte de uma declaração `mutable` podem ser recuperados para um valor diferente mais tarde no código.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="ddfa9-173">Uma declaração de ligação mutável consiste na palavra-chave `mutable`, seguida de um símbolo ou símbolo, um sinal igual `=`, uma expressão para ligar o símbolo(s) e um ponto evículo terminante.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="ddfa9-174">O tipo de símbolo s de atado é inferido com base na expressão do lado direito.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="ddfa9-175">Se um símbolo for recuperado mais tarde no código, o seu tipo não muda, e o valor vinculado tem de ser compatível com esse tipo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="ddfa9-176">Reenção de símbolos mutáveis</span><span class="sxs-lookup"><span data-stu-id="ddfa9-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="ddfa9-177">Uma variável mutável pode ser recuperada usando uma declaração `set`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="ddfa9-178">Tal reencência consiste na palavra-chave `set`, seguida de um símbolo ou símbolo, um sinal igual `=`, uma expressão para religar o símbolo(s) a, e um ponto evículo terminante.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="ddfa9-179">O valor deve ser compatível com o ou os tipos do símbolo a que está ligado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="ddfa9-180">Declaração de Candidatura e Reatribuição</span><span class="sxs-lookup"><span data-stu-id="ddfa9-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="ddfa9-181">Um tipo particular de declaração de set a que nos referimos como uma declaração de aplicação e reatribuição fornece uma forma conveniente de concatenação se o lado direito consistir na aplicação de um operador binário e o resultado é ser ressaltado para o argumento esquerdo para o operador.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="ddfa9-182">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="ddfa9-183">incrementa o valor do contador `counter` em cada iteração do ciclo `for`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="ddfa9-184">O código acima é equivalente a</span><span class="sxs-lookup"><span data-stu-id="ddfa9-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="ddfa9-185">Estão disponíveis declarações semelhantes para todos os operadores binários em que o tipo do lado esquerdo corresponde ao tipo de expressão.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="ddfa9-186">Isto fornece, por exemplo, uma forma conveniente de acumular valores:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="ddfa9-187">Declaração de atualização e reatribuição</span><span class="sxs-lookup"><span data-stu-id="ddfa9-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="ddfa9-188">Existe uma concatenação semelhante para expressões de cópia e atualização no lado direito.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="ddfa9-189">Consequentemente, existem declarações de atualização e reatribuição para itens nomeados em tipos definidos pelo utilizador, bem como para itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ElementwisePlus(reals : Double[], ims : Double[]) : Complex[] {
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

<span data-ttu-id="ddfa9-190">No caso das matrizes, as nossas bibliotecas padrão contêm as ferramentas necessárias para muitas necessidades comuns de inicialização e manipulação de matrizes, ajudando assim a evitar ter de atualizar itens de matriz em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="ddfa9-191">As declarações de atualização e reatribuição fornecem uma alternativa, se necessário:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-191">Update-and-reassign statements provide an alternative if needed:</span></span>

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

> [!TIP]   
> <span data-ttu-id="ddfa9-192">Evite a utilização desnecessária de declarações de atualização e reatribuição, aproveitando as ferramentas fornecidas em <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="ddfa9-193">A função</span><span class="sxs-lookup"><span data-stu-id="ddfa9-193">The function</span></span>
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="ddfa9-194">por exemplo, pode simplesmente ser simplificado utilizando a função `ConstantArray` em `Microsoft.Quantum.Arrays`, e devolvendo uma expressão de cópia e atualização:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="ddfa9-195">Âmbitos vinculativos</span><span class="sxs-lookup"><span data-stu-id="ddfa9-195">Binding Scopes</span></span>

<span data-ttu-id="ddfa9-196">Em geral, as ligações dos símbolos desbloqueiam o seu alcance e tornam-se inoperantes no final do bloco de declaração em que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="ddfa9-197">Há duas exceções a esta regra:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="ddfa9-198">A ligação da variável de ciclo de um ciclo de `for` está no âmbito do corpo do laço para o loop, mas não após o fim do laço.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="ddfa9-199">Todas as três porções de um `repeat`/`until` loop (o corpo, o teste e a fixação) são tratadas como um único âmbito, pelo que os símbolos que estão ligados no corpo estão disponíveis no teste e na fixação.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="ddfa9-200">Para ambos os tipos de loops, cada passe através do loop executa no seu próprio âmbito, pelo que as encadernações de um passe anterior não estão disponíveis num passe posterior.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="ddfa9-201">As ligações dos símbolos dos blocos exteriores são herdadas por blocos internos.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="ddfa9-202">Um símbolo só pode ser ligado uma vez por bloco; é ilegal definir um símbolo com o mesmo nome que outro símbolo que está dentro do âmbito (sem "sombra").</span><span class="sxs-lookup"><span data-stu-id="ddfa9-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="ddfa9-203">As seguintes sequências seriam legais:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="ddfa9-204">e em</span><span class="sxs-lookup"><span data-stu-id="ddfa9-204">and</span></span>

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

<span data-ttu-id="ddfa9-205">Mas isto seria ilegal.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="ddfa9-206">como:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="ddfa9-207">Fluxo de Controlo</span><span class="sxs-lookup"><span data-stu-id="ddfa9-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="ddfa9-208">Para Loop</span><span class="sxs-lookup"><span data-stu-id="ddfa9-208">For Loop</span></span>

<span data-ttu-id="ddfa9-209">A declaração de `for` suporta a iteração sobre uma gama de inteiros ou sobre uma matriz.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="ddfa9-210">A declaração consiste na palavra-chave `for`, um parêntese aberto `(`, seguido de um símbolo ou símbolo, a palavra-chave `in`, uma expressão de tipo `Range` ou matriz, um parêntese próximo `)`, e um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="ddfa9-211">O bloco de declaração (o corpo do laço) é executado repetidamente, com os símbolos definidos (a variável do laço(s)ligadoa a cada valor na gama ou matriz.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="ddfa9-212">Note que se a expressão de alcance avaliar para um alcance ou matriz vazio, o corpo não será executado de todo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="ddfa9-213">A expressão é totalmente avaliada antes de entrar no loop, e não mudará enquanto o loop estiver executando.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="ddfa9-214">A ligação dos símbolos declarados é imutável e segue as mesmas regras que outras encadernações variáveis.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="ddfa9-215">Em particular, é possível destruir, por exemplo, itens de matriz para uma iteração sobre uma matriz aquando da atribuição à variável de loop.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="ddfa9-216">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-216">For example,</span></span>

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
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

<span data-ttu-id="ddfa9-217">A variável do loop é ligada a cada entrada do corpo em loop, e desamarrada na extremidade do corpo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="ddfa9-218">Em particular, a variável de loop não está ligada após a conclusão do ciclo para o loop.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="ddfa9-219">Loop de repetição até ao sucesso</span><span class="sxs-lookup"><span data-stu-id="ddfa9-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="ddfa9-220">A declaração `repeat` apoia o padrão quântico de "repetir até ao sucesso".</span><span class="sxs-lookup"><span data-stu-id="ddfa9-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="ddfa9-221">Consiste na palavra-chave `repeat`, seguida de um bloco de declaração (o corpo _de loop),_ a palavra-chave `until`, uma expressão booleana, e ou um ponto evículo terminando ou a palavra-chave `fixup` seguido de outro bloco de declaração (a _fixação)._</span><span class="sxs-lookup"><span data-stu-id="ddfa9-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="ddfa9-222">O corpo, a condição e a fixação do laço são considerados um único âmbito, pelo que os símbolos ligados ao corpo estão disponíveis na condição e fixação.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

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

<span data-ttu-id="ddfa9-223">O corpo do loop é executado, e então a condição é avaliada.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="ddfa9-224">Se a condição for verdadeira, então a declaração é completada; caso contrário, a correção é executada, e a declaração é reexecutada a partir do corpo do loop.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="ddfa9-225">Note que a conclusão da execução da fixação termina o âmbito da declaração, de modo a que as ligações de símbolos efetuadas durante o corpo ou a fixação não estejam disponíveis em repetições subsequentes.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="ddfa9-226">Por exemplo, o seguinte código é um circuito probabilístico que implementa um importante portão de rotação $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ utilizando os portões Hadamard e T.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="ddfa9-227">O loop termina em $\frac{8}{5}repetições de $, em média.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-227">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="ddfa9-228">Ver [*Repeat-Until-Success: Decomposição não-determinística de unitários monoqubit*](https://arxiv.org/abs/1311.1074) (Paetznick e Svore, 2014) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

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

> [!TIP]   
> <span data-ttu-id="ddfa9-229">Evite utilizar laços de repetição até ao sucesso dentro das funções.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="ddfa9-230">A funcionalidade correspondente é fornecida através de loops nas funções.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="ddfa9-231">Enquanto Loop</span><span class="sxs-lookup"><span data-stu-id="ddfa9-231">While Loop</span></span>

<span data-ttu-id="ddfa9-232">Os padrões de repetição até ao sucesso têm uma conotação muito quântica específica.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="ddfa9-233">Eles são amplamente usados em classes particulares de algoritmos quânticos - daí a construção de linguagem dedicada em Q#.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="ddfa9-234">No entanto, os laços que se rompem com base numa condição e cujo comprimento de execução é, portanto, desconhecido no tempo de compilação precisam de ser tratados com especial cuidado num tempo de execução quântico.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="ddfa9-235">A sua utilização dentro de funções, por outro lado, não é problemática, uma vez que estas contêm apenas código que será executado em hardware convencional (não quântico).</span><span class="sxs-lookup"><span data-stu-id="ddfa9-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="ddfa9-236">Q# apoia, portanto, a utilização de laços enquanto as funções apenas.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="ddfa9-237">Uma declaração `while` consiste na palavra-chave `while`, um `(`de parênteses abertas , uma condição (isto é, uma expressão booleana), um parêntese próximo `)`, e um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="ddfa9-238">O bloco de declaração (o corpo do laço) é executado desde que a condição avalie para `true`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="ddfa9-239">Declaração Condicional</span><span class="sxs-lookup"><span data-stu-id="ddfa9-239">Conditional Statement</span></span>

<span data-ttu-id="ddfa9-240">A declaração `if` apoia a execução condicional.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="ddfa9-241">Consiste na palavra-chave `if`, um parêntese aberto `(`, uma expressão booleana, um parêntese próximo `)`, e um bloco de declaração (o _bloco de então)._</span><span class="sxs-lookup"><span data-stu-id="ddfa9-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="ddfa9-242">Isto pode ser seguido por qualquer número de cláusulas se, cada uma das quais consiste na palavra-chave `elif`, um parêntese aberto `(`, uma expressão booleana, um parêntese próximo `)`, e um bloco de declaração (o _bloco de outra sea)._</span><span class="sxs-lookup"><span data-stu-id="ddfa9-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="ddfa9-243">Finalmente, a declaração pode terminar opcionalmente com uma outra cláusula, que consiste na palavra-chave `else` seguida de outro bloco de declaração (o _bloco de outra_ si).</span><span class="sxs-lookup"><span data-stu-id="ddfa9-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="ddfa9-244">A condição é avaliada, e se for verdade, o bloco de então é executado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="ddfa9-245">Se a condição for falsa, então a condição de outra pessoa é avaliada; se for verdade, que o bloco mais se for executado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="ddfa9-246">Caso contrário, o segundo bloco se for testado, e depois o terceiro, e assim por diante, até que seja encontrada uma cláusula com uma condição real ou não haja mais cláusulas se.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="ddfa9-247">Se a condição original e todas as cláusulas se forem avaliadas como falsas, o outro bloco é executado se um for fornecido.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="ddfa9-248">Note que qualquer bloco executado é executado no seu próprio âmbito.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="ddfa9-249">As encadernações feitas dentro de um bloco então, se, ou então, não são visíveis após o fim da declaração se.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="ddfa9-250">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="ddfa9-251">ou</span><span class="sxs-lookup"><span data-stu-id="ddfa9-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="ddfa9-252">Devolução</span><span class="sxs-lookup"><span data-stu-id="ddfa9-252">Return</span></span>

<span data-ttu-id="ddfa9-253">A declaração de devolução termina a execução de uma operação ou função e devolve um valor ao chamador.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="ddfa9-254">Consiste na palavra-chave `return`, seguida de uma expressão do tipo apropriado, e de um ponto evíomina terminando.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="ddfa9-255">Um insensível que devolve uma tuple vazia, `()`, não requer uma declaração de devolução.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="ddfa9-256">Se for desejada uma saída antecipada, `return ()` podem ser utilizados neste caso.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="ddfa9-257">Os callables que devolvem qualquer outro tipo requerem uma declaração final de devolução.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="ddfa9-258">Não há um número máximo de declarações de devolução dentro de uma operação.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="ddfa9-259">O compilador pode emitir um aviso se as declarações seguirem uma declaração de devolução dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="ddfa9-260">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="ddfa9-261">ou</span><span class="sxs-lookup"><span data-stu-id="ddfa9-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="ddfa9-262">ou</span><span class="sxs-lookup"><span data-stu-id="ddfa9-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="ddfa9-263">Falha</span><span class="sxs-lookup"><span data-stu-id="ddfa9-263">Fail</span></span>

<span data-ttu-id="ddfa9-264">A declaração de falha termina a execução de uma operação e devolve um valor de erro ao chamador.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="ddfa9-265">Consiste na palavra-chave `fail`, seguida de uma corda e de um ponto evío minado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="ddfa9-266">A corda é devolvida ao condutor clássico como mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="ddfa9-267">Não existe qualquer restrição ao número de declarações falhadas no âmbito de uma operação.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="ddfa9-268">O compilador pode emitir um aviso se as declarações seguirem uma declaração de falha dentro de um bloco.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="ddfa9-269">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="ddfa9-270">ou</span><span class="sxs-lookup"><span data-stu-id="ddfa9-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="ddfa9-271">Gestão qubit</span><span class="sxs-lookup"><span data-stu-id="ddfa9-271">Qubit Management</span></span>

<span data-ttu-id="ddfa9-272">Note que nenhuma destas declarações é permitida dentro do corpo de uma função.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="ddfa9-273">Só são válidos dentro das operações.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="ddfa9-274">Qubits limpos</span><span class="sxs-lookup"><span data-stu-id="ddfa9-274">Clean Qubits</span></span>

<span data-ttu-id="ddfa9-275">A declaração `using` é utilizada para adquirir novos qubits para utilização durante um bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="ddfa9-276">Os qubits são garantidos para serem inicializados para o estado computacional `Zero`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="ddfa9-277">Os qubits devem estar no estado de `Zero` computacional no final do bloco de declaração; simuladores são encorajados a impor isto.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="ddfa9-278">A declaração consiste na palavra-chave `using`, seguida de um parêntese aberto `(`, uma ligação, um parêntese próximo `)`, e o bloco de declaração dentro do qual estarão disponíveis os qubits.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="ddfa9-279">A ligação segue o mesmo padrão que as declarações `let`: um único símbolo ou uma tuple de símbolos, seguido de um sinal igual `=`, e um único valor ou uma túnica correspondente de iniciais.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="ddfa9-280">Os iniciais estão disponíveis para um único qubit, indicado como `Qubit()`, ou um conjunto de qubits, indicados por `Qubit[`, uma expressão `Int` e `]`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="ddfa9-281">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-281">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a><span data-ttu-id="ddfa9-282">Qubits emprestados</span><span class="sxs-lookup"><span data-stu-id="ddfa9-282">Borrowed Qubits</span></span>

<span data-ttu-id="ddfa9-283">A declaração `borrowing` é utilizada para obter qubits para uso temporário.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="ddfa9-284">A declaração consiste na palavra-chave `borrowing`, seguida de um parêntese aberto `(`, uma ligação, um parêntese próximo `)`, e o bloco de declaração dentro do qual estarão disponíveis os qubits.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="ddfa9-285">A encadernação segue o mesmo padrão e regras que a de uma declaração `using`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="ddfa9-286">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-286">For example,</span></span>

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="ddfa9-287">Os qubits emprestados estão num estado desconhecido e saem do âmbito no final do bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="ddfa9-288">O mutuário compromete-se a deixar os qubits no mesmo estado em que estavam quando foram emprestados, ou seja, o seu estado no início e no final do bloco de declaração deverá ser o mesmo.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="ddfa9-289">Este Estado, em particular, não é necessariamente um estado clássico, de tal forma que, na maioria dos casos, os âmbitos de empréstimo não devem conter medições.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="ddfa9-290">Consulte [*factoring usando 2n+2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) como um exemplo de utilização de qubit emprestado.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-290">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of borrowed qubit use.</span></span>

<span data-ttu-id="ddfa9-291">Ao pedir qubits emprestados, o sistema tentará primeiro preencher o pedido de qubits que estão em uso, mas que não são acedidos durante o corpo da declaração de `borrowing`.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-291">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="ddfa9-292">Se não houver qubits suficientes, então irá alocar novos qubits para completar o pedido.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-292">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="ddfa9-293">Conjugações</span><span class="sxs-lookup"><span data-stu-id="ddfa9-293">Conjugations</span></span>

<span data-ttu-id="ddfa9-294">Em contraste com as partes clássicas, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejados no restante cálculo se os qubits ainda estiverem emaranhados.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-294">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="ddfa9-295">Isto pode ser evitado por "desfazer" corretamente as computações realizadas antes de libertar a memória.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-295">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="ddfa9-296">Um padrão comum na computação quântica é, portanto, o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-296">A common pattern in quantum computing is hence the following:</span></span> 

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

:novo: <span data-ttu-id="ddfa9-297">A partir do nosso lançamento 0.9, apoiamos uma declaração de conjugação que implementa a transformação acima.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-297">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="ddfa9-298">Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="ddfa9-298">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="ddfa9-299">Tal declaração de conjugação torna-se obviamente muito mais útil se a transformação exterior e interior não estiver prontamente disponível como operações, mas em vez disso são mais convenientes para descrever por um bloco composto por várias declarações.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-299">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="ddfa9-300">A transformação inversa para as declarações definidas no bloco interior é automaticamente gerada pelo compilador e executada após a conclusão do bloco de aplicação.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-300">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="ddfa9-301">Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente a adjoint do cálculo no bloco interior.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-301">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="ddfa9-302">Declarações de avaliação de expressão</span><span class="sxs-lookup"><span data-stu-id="ddfa9-302">Expression Evaluation Statements</span></span>

<span data-ttu-id="ddfa9-303">Qualquer expressão de chamada de `Unit` pode ser usada como uma declaração.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-303">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="ddfa9-304">Isto é principalmente útil quando se ligam operações sobre qubits que devolvem `Unit` porque o objetivo da declaração é modificar o estado quântico implícito.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-304">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="ddfa9-305">As declarações de avaliação da expressão requerem um ponto e vírgula terminando.</span><span class="sxs-lookup"><span data-stu-id="ddfa9-305">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="ddfa9-306">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="ddfa9-306">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
