---
title: Q# Estrutura de Arquivo
description: Descreve a estrutura e a sintaxe de um ficheiro Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: cbee92c6d7e765237a7a42532dd7012b51421708
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430973"
---
# <a name="q-file-structure"></a><span data-ttu-id="c7e90-103">Q# Estrutura de Arquivo</span><span class="sxs-lookup"><span data-stu-id="c7e90-103">Q# File Structure</span></span>

<span data-ttu-id="c7e90-104">Cada operação, função e tipo definido pelo utilizador é definido dentro de um espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="c7e90-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="c7e90-105">Um ficheiro Q# consiste numa sequência de *declarações*de espaço de nome .</span><span class="sxs-lookup"><span data-stu-id="c7e90-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="c7e90-106">Cada declaração de espaço de nome contém declarações para tipos, operações e funções definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c7e90-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="c7e90-107">Uma declaração de espaço-nome pode conter qualquer número de cada tipo de declaração, e em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="c7e90-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="c7e90-108">Siga estes links para obter mais detalhes sobre a declaração [de tipos definidos](xref:microsoft.quantum.guide.types#user-defined-types)pelo utilizador, [operações](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funções](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) dentro de um espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="c7e90-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="c7e90-109">O único texto que pode aparecer fora de uma declaração de espaço de nome são os comentários.</span><span class="sxs-lookup"><span data-stu-id="c7e90-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="c7e90-110">Em particular, os comentários documentais (mais detalhes abaixo) para um espaço de nome precedem a declaração.</span><span class="sxs-lookup"><span data-stu-id="c7e90-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="c7e90-111">Declarações de espaço de nome</span><span class="sxs-lookup"><span data-stu-id="c7e90-111">Namespace Declarations</span></span>

<span data-ttu-id="c7e90-112">Um ficheiro Q# terá normalmente uma declaração de espaço-nome, mas pode ter nenhuma (e estar vazia ou apenas conter comentários) ou pode conter vários espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="c7e90-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="c7e90-113">As declarações de espaço-nome não podem ser aninhadas.</span><span class="sxs-lookup"><span data-stu-id="c7e90-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="c7e90-114">O mesmo espaço de nome pode ser declarado em vários ficheiros Q# que são compilados em conjunto, desde que não existam declarações de tipo, operação ou função com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="c7e90-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="c7e90-115">Em particular, é inválido definir o mesmo tipo no mesmo espaço de nome em vários ficheiros, mesmo que as declarações sejam idênticas.</span><span class="sxs-lookup"><span data-stu-id="c7e90-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="c7e90-116">Uma declaração de espaço de nome consiste na palavra-chave, seguida do nome do espaço de `namespace` nome, de uma cinta `{` aberta, das declarações contidas no espaço de nome, e de uma cinta de `}` proximidade.</span><span class="sxs-lookup"><span data-stu-id="c7e90-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="c7e90-117">Os nomes do espaço de nome seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por períodos `.` .</span><span class="sxs-lookup"><span data-stu-id="c7e90-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="c7e90-118">Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` são nomes de espaço de nome válidos.</span><span class="sxs-lookup"><span data-stu-id="c7e90-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="c7e90-119">Por convenção, os símbolos de um nome de espaço de nome são capitalizados, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="c7e90-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="c7e90-120">As referências a tipos ou callables declarados mais abaixo num ficheiro são devidamente resolvidas; não há necessidade de o tipo, operação ou declaração de função preceder uma referência a ele.</span><span class="sxs-lookup"><span data-stu-id="c7e90-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="c7e90-121">Diretivas abertas</span><span class="sxs-lookup"><span data-stu-id="c7e90-121">Open Directives</span></span>

<span data-ttu-id="c7e90-122">Dentro de um bloco de espaço-nome, a `open` diretiva pode ser utilizada para importar todos os tipos e callables declarados num determinado espaço de nome e encaminhá-los pelo seu nome não qualificado.</span><span class="sxs-lookup"><span data-stu-id="c7e90-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="c7e90-123">Tal `open` diretiva consiste na `open` palavra-chave, seguida do espaço-nome a abrir e de um ponto evíceo que termina.</span><span class="sxs-lookup"><span data-stu-id="c7e90-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="c7e90-124">Todas as `open` diretivas devem apresentar-se antes de quaisquer `function` , ou `operation` `newtype` declarações no bloco de espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="c7e90-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="c7e90-125">Opcionalmente, pode ser definido um nome curto para o espaço de nome aberto de modo a que todos os elementos desse espaço de nome possam (e precisam) ser qualificados pelo nome curto definido.</span><span class="sxs-lookup"><span data-stu-id="c7e90-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="c7e90-126">Por exemplo, dada a seguinte declaração de espaço de nome e diretivas abertas,</span><span class="sxs-lookup"><span data-stu-id="c7e90-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="c7e90-127">se uma operação que declaramos usa uma `Op` `Microsoft.Quantum.Intrinsic` operação, nós a chamaríamos simplesmente usando `Op` .</span><span class="sxs-lookup"><span data-stu-id="c7e90-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="c7e90-128">No entanto, se quiséssemos uma chamada de uma determinada `Fn` `Microsoft.Quantum.Math` função, teríamos de chamá-la de `Math.Fn` utilização.</span><span class="sxs-lookup"><span data-stu-id="c7e90-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="c7e90-129">A `open` diretiva aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.</span><span class="sxs-lookup"><span data-stu-id="c7e90-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="c7e90-130">Assim, se definissemos um espaço de nome adicional no mesmo ficheiro Q# que `NS` acima, quaisquer operações/funções/tipos definidos no segundo espaço de nome não teriam acesso a nada a partir `Microsoft.Quantum.Intrinsic` ou a menos que `Microsoft.Quantum.Math` repetissemos as diretivas abertas nele.</span><span class="sxs-lookup"><span data-stu-id="c7e90-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="c7e90-131">Um tipo ou callable definido em outro espaço de nome que *não* esteja aberto no espaço de nome atual deve ser referenciado pelo seu nome totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="c7e90-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="c7e90-132">Por exemplo, uma operação denominada a partir do espaço de `Op` `X.Y` nome deve ser referenciada pelo seu nome totalmente `X.Y.Op` qualificado, a menos que o espaço de `X.Y` nome tenha sido aberto mais cedo no bloco atual.</span><span class="sxs-lookup"><span data-stu-id="c7e90-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="c7e90-133">Como mencionado acima, mesmo que o espaço de `X` nome tenha sido aberto, não é possível fazer referência à operação como `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="c7e90-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="c7e90-134">Se um nome curto `Z` tiver sido definido nesse espaço de nome e `X.Y` arquivo, então `Op` deve ser referido como `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="c7e90-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="c7e90-135">Normalmente, é melhor incluir um espaço de nome através da utilização de uma `open` diretiva.</span><span class="sxs-lookup"><span data-stu-id="c7e90-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="c7e90-136">É necessário utilizar um nome totalmente qualificado se dois espaços de nome definirem construções com o mesmo nome, e a fonte atual utiliza construções de ambos.</span><span class="sxs-lookup"><span data-stu-id="c7e90-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="c7e90-137">Q# segue as mesmas regras para nomear outras línguas .NET.</span><span class="sxs-lookup"><span data-stu-id="c7e90-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="c7e90-138">No entanto, Q# não suporta referências relativas a espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="c7e90-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="c7e90-139">Ou seja, se o espaço de nome `a.b` supor, uma referência a uma operação nomeada `c.d` *não* será resolvida a uma operação com nome completo `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="c7e90-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="c7e90-140">Formatação</span><span class="sxs-lookup"><span data-stu-id="c7e90-140">Formatting</span></span>

<span data-ttu-id="c7e90-141">A maioria das declarações e diretivas q# terminam com um ponto evígula terminando, `;` .</span><span class="sxs-lookup"><span data-stu-id="c7e90-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="c7e90-142">Declarações e declarações como e que terminam com um bloco de `for` `operation` declaração (ver abaixo) não requerem um ponto evívio terminando.</span><span class="sxs-lookup"><span data-stu-id="c7e90-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="c7e90-143">Cada descrição da declaração observa se o ponto evículo terminando é necessário.</span><span class="sxs-lookup"><span data-stu-id="c7e90-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="c7e90-144">Declarações, como expressões, declarações e diretivas, podem ser quebradas em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="c7e90-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="c7e90-145">Deve evitar-se várias declarações numa única linha.</span><span class="sxs-lookup"><span data-stu-id="c7e90-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="c7e90-146">Blocos de Declaração</span><span class="sxs-lookup"><span data-stu-id="c7e90-146">Statement Blocks</span></span>

<span data-ttu-id="c7e90-147">As declarações de Q# são agruparadas em blocos de declaração.</span><span class="sxs-lookup"><span data-stu-id="c7e90-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="c7e90-148">Um bloco de declaração começa com uma abertura `{` e termina com um fecho `}` .</span><span class="sxs-lookup"><span data-stu-id="c7e90-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="c7e90-149">Um bloco de declaração que seja lexicamente fechado dentro de outro bloco é considerado um subbloco do bloco contendo; contendo e subblocos também são chamados blocos exteriores e internos.</span><span class="sxs-lookup"><span data-stu-id="c7e90-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="c7e90-150">Comentários</span><span class="sxs-lookup"><span data-stu-id="c7e90-150">Comments</span></span>

<span data-ttu-id="c7e90-151">Os comentários começam com dois cortes para a `//` frente, e continuam até ao fim da linha.</span><span class="sxs-lookup"><span data-stu-id="c7e90-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="c7e90-152">Um comentário pode aparecer em qualquer lugar num ficheiro de origem Q#.</span><span class="sxs-lookup"><span data-stu-id="c7e90-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="c7e90-153">Comentários de Documentação</span><span class="sxs-lookup"><span data-stu-id="c7e90-153">Documentation Comments</span></span>

<span data-ttu-id="c7e90-154">Os comentários que começam com três cortes `///` dianteiros, são tratados especialmente pelo compilador quando aparecem imediatamente antes de um espaço de nome, operação, especialização, função ou definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="c7e90-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="c7e90-155">Nesse caso, os seus conteúdos são tomados como documentação para o tipo definido de callable ou definido pelo utilizador, como para outros idiomas .NET.</span><span class="sxs-lookup"><span data-stu-id="c7e90-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="c7e90-156">Dentro dos comentários, o `///` texto a aparecer como parte da documentação da API é formatado como [Markdown](https://daringfireball.net/projects/markdown/syntax), com diferentes partes da documentação a serem indicadas por cabeçalhos especialmente nomeados.</span><span class="sxs-lookup"><span data-stu-id="c7e90-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="c7e90-157">Como extensão ao Markdown, as referências cruzadas a operações, funções e tipos definidos pelo utilizador em Q# podem ser incluídas utilizando o , onde é substituído pelo nome totalmente qualificado do objeto de código que está a `@"<ref target>"` `<ref target>` ser referenciado.</span><span class="sxs-lookup"><span data-stu-id="c7e90-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="c7e90-158">Opcionalmente, um motor de documentação também pode suportar extensões de Markdown adicionais.</span><span class="sxs-lookup"><span data-stu-id="c7e90-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="c7e90-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c7e90-159">For example:</span></span>

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

<span data-ttu-id="c7e90-160">Os seguintes nomes são reconhecidos como cabeçalhos de comentário documentais.</span><span class="sxs-lookup"><span data-stu-id="c7e90-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="c7e90-161">**Resumo**: Um resumo curto do comportamento de uma função ou operação, ou do propósito de um tipo.</span><span class="sxs-lookup"><span data-stu-id="c7e90-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="c7e90-162">O primeiro parágrafo do resumo é utilizado para informações sobre pairar.</span><span class="sxs-lookup"><span data-stu-id="c7e90-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="c7e90-163">Deve ser um texto simples.</span><span class="sxs-lookup"><span data-stu-id="c7e90-163">It should be plain text.</span></span>
- <span data-ttu-id="c7e90-164">**Descrição**: Uma descrição do comportamento de uma função ou operação, ou do propósito de um tipo.</span><span class="sxs-lookup"><span data-stu-id="c7e90-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="c7e90-165">O resumo e a descrição são concatenados para formar o ficheiro de documentação gerado para a função, operação ou tipo.</span><span class="sxs-lookup"><span data-stu-id="c7e90-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="c7e90-166">A descrição pode conter símbolos e equações formatados em linha LaTeX.</span><span class="sxs-lookup"><span data-stu-id="c7e90-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="c7e90-167">**Entrada**: Uma descrição do tuple de entrada para uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="c7e90-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="c7e90-168">Pode conter subsecções de Markdown adicionais indicando cada elemento individual da tuple de entrada.</span><span class="sxs-lookup"><span data-stu-id="c7e90-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="c7e90-169">**Saída**: Uma descrição do tuple devolvido por uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="c7e90-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="c7e90-170">**Parâmetros do tipo**: Uma secção vazia que contém uma subsecção adicional para cada parâmetro genérico do tipo.</span><span class="sxs-lookup"><span data-stu-id="c7e90-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="c7e90-171">**Exemplo**: Um pequeno exemplo do funcionamento, função ou tipo de utilização.</span><span class="sxs-lookup"><span data-stu-id="c7e90-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="c7e90-172">**Observações**: Prosa diversa que descreve algum aspeto da operação, função ou tipo.</span><span class="sxs-lookup"><span data-stu-id="c7e90-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="c7e90-173">**Ver Também:** Uma lista de nomes totalmente qualificados que indicam funções, operações ou tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c7e90-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="c7e90-174">**Referências**: Uma lista de referências e citações para o artigo que está a ser documentado.</span><span class="sxs-lookup"><span data-stu-id="c7e90-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="whats-next"></a><span data-ttu-id="c7e90-175">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="c7e90-175">What's Next?</span></span>
<span data-ttu-id="c7e90-176">Conheça [operações e funções](xref:microsoft.quantum.guide.operationsfunctions) em Q#.</span><span class="sxs-lookup"><span data-stu-id="c7e90-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>