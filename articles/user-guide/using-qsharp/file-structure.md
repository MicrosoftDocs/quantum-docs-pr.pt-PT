---
title: Q#Estrutura de Arquivos
description: Descreve a estrutura e a sintaxe de um Q# ficheiro.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac73962b1a718cd04aa87ee3476c66781fe3ac2b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867935"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="fca32-103">Q#Estrutura de Arquivos</span><span class="sxs-lookup"><span data-stu-id="fca32-103">Q# File Structure</span></span>

<span data-ttu-id="fca32-104">Um Q# ficheiro consiste numa sequência de *declarações de espaço de nome*.</span><span class="sxs-lookup"><span data-stu-id="fca32-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="fca32-105">Cada declaração de espaço de nome contém declarações para tipos, operações e funções definidos pelo utilizador, e pode conter qualquer número de cada tipo de declaração e em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="fca32-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="fca32-106">Para obter mais informações sobre declarações dentro de um espaço de nome, consulte tipos, [operações](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funções definidos](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [pelo utilizador.](xref:microsoft.quantum.guide.types#user-defined-types)</span><span class="sxs-lookup"><span data-stu-id="fca32-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="fca32-107">O único texto que pode aparecer fora de uma declaração de espaço de nome são os comentários.</span><span class="sxs-lookup"><span data-stu-id="fca32-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="fca32-108">Em particular, os comentários documentais relativos a um espaço de nome precedem a declaração.</span><span class="sxs-lookup"><span data-stu-id="fca32-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="fca32-109">Para mais informações, consulte [comentários de documentação](#documentation-comments) neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fca32-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="fca32-110">Declarações de espaço de nome</span><span class="sxs-lookup"><span data-stu-id="fca32-110">Namespace Declarations</span></span>

<span data-ttu-id="fca32-111">Um Q# ficheiro normalmente tem apenas uma declaração de espaço de nome, mas pode não ter nenhuma (e estar vazia ou apenas conter comentários) ou pode conter vários espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="fca32-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="fca32-112">As declarações do espaço de nome não podem ser aninhadas.</span><span class="sxs-lookup"><span data-stu-id="fca32-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="fca32-113">Pode declarar o mesmo espaço de nome em Q# vários ficheiros que são compilados em conjunto, desde que não existam declarações de tipo, operação ou função com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="fca32-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="fca32-114">Em particular, é inválido definir o mesmo tipo no mesmo espaço de identificação em vários ficheiros, mesmo que as declarações sejam idênticas.</span><span class="sxs-lookup"><span data-stu-id="fca32-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="fca32-115">Uma declaração de espaço de nome consiste na palavra-chave, `namespace` seguida do nome do espaço de nome, e das declarações contidas no espaço de nome incluído em aparelhos. `{ }`</span><span class="sxs-lookup"><span data-stu-id="fca32-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="fca32-116">Os nomes do espaço de nome seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por períodos `.` .</span><span class="sxs-lookup"><span data-stu-id="fca32-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="fca32-117">Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` são nomes válidos para o espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="fca32-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="fca32-118">Por convenção, capitalize os símbolos num nome de espaço de nome, no entanto, isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="fca32-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="fca32-119">Referências a tipos ou chamadas declaradas mais abaixo numa resolução de ficheiros corretamente; não há necessidade de que o tipo, o funcionamento ou a declaração de função precedam uma referência ao mesmo.</span><span class="sxs-lookup"><span data-stu-id="fca32-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="fca32-120">Diretivas abertas</span><span class="sxs-lookup"><span data-stu-id="fca32-120">Open Directives</span></span>

<span data-ttu-id="fca32-121">Dentro de um bloco de espaço de nome, utilize a `open` diretiva para importar todos os tipos e callables declarados num determinado espaço de nome e consulte-os pelo seu nome não qualificado.</span><span class="sxs-lookup"><span data-stu-id="fca32-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="fca32-122">Esta `open` diretiva consiste na `open` palavra-chave, seguida do espaço de nome a abrir e de um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="fca32-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="fca32-123">Todas as `open` diretivas devem ser apresentadas antes de qualquer `function` , ou `operation` `newtype` declarações no bloco de espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="fca32-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="fca32-124">Opcionalmente, pode definir um nome curto para o espaço de nome aberto.</span><span class="sxs-lookup"><span data-stu-id="fca32-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="fca32-125">Se um nome curto for definido, deve qualificar todos os elementos desse espaço pelo nome curto definido.</span><span class="sxs-lookup"><span data-stu-id="fca32-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="fca32-126">Por exemplo, tendo em conta a seguinte declaração de espaço de nome e diretivas abertas,</span><span class="sxs-lookup"><span data-stu-id="fca32-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="fca32-127">se uma operação declarada utilizar uma operação `Op` a partir de , `Microsoft.Quantum.Intrinsic` chame-a simplesmente utilizando `Op` .</span><span class="sxs-lookup"><span data-stu-id="fca32-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="fca32-128">No entanto, para chamar uma determinada função `Fn` de `Microsoft.Quantum.Math` , deve chamá-lo de uso `Math.Fn` .</span><span class="sxs-lookup"><span data-stu-id="fca32-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="fca32-129">A `open` diretiva aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.</span><span class="sxs-lookup"><span data-stu-id="fca32-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="fca32-130">Assim, se definir um espaço de nome adicional no mesmo Q# ficheiro `NS` que anteriormente, então quaisquer operações/funções/tipos definidos no segundo espaço de nome não teriam acesso a nada a partir `Microsoft.Quantum.Intrinsic` ou a menos que `Microsoft.Quantum.Math` repetisse as diretivas abertas neles.</span><span class="sxs-lookup"><span data-stu-id="fca32-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="fca32-131">Para fazer referência a um tipo ou chamada definido noutro espaço de nome que *não* esteja aberto no espaço de nomes atual, deve fazê-lo referenciar pelo seu nome totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="fca32-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="fca32-132">Por exemplo, dada uma operação denominada `Op` a partir do espaço de `X.Y` nome:</span><span class="sxs-lookup"><span data-stu-id="fca32-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="fca32-133">Deve fazê-lo referenciar pelo seu nome totalmente `X.Y.Op` qualificado, a menos que o `X.Y` espaço de nome tenha sido aberto mais cedo no bloco atual.</span><span class="sxs-lookup"><span data-stu-id="fca32-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="fca32-134">Mesmo que o `X` espaço de nome seja aberto, não é possível referenciar a operação como `Y.Op` .</span><span class="sxs-lookup"><span data-stu-id="fca32-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="fca32-135">Se definir o nome curto `Z` para esse espaço e arquivo de `X.Y` nomes, deve fazer referência `Op` como `Z.Op` .</span><span class="sxs-lookup"><span data-stu-id="fca32-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="fca32-136">Normalmente, é melhor incluir um espaço de nome através de uma `open` diretiva.</span><span class="sxs-lookup"><span data-stu-id="fca32-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="fca32-137">A utilização de um nome totalmente qualificado é necessária se dois espaços de nome definirem construções com o mesmo nome, e a fonte atual utiliza construções de ambos.</span><span class="sxs-lookup"><span data-stu-id="fca32-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="fca32-138">Q#segue as mesmas regras para nomear como outras línguas .NET.</span><span class="sxs-lookup"><span data-stu-id="fca32-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="fca32-139">No entanto, Q# não suporta referências relativas a espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="fca32-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="fca32-140">Por exemplo, se o espaço de nome `a.b` estiver aberto, uma referência a uma operação nomeada `c.d` *não* se resolve a uma operação com nome completo `a.b.c.d` .</span><span class="sxs-lookup"><span data-stu-id="fca32-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="fca32-141">Formatação</span><span class="sxs-lookup"><span data-stu-id="fca32-141">Formatting</span></span>

<span data-ttu-id="fca32-142">A maioria das Q# declarações e diretivas terminam com um semicolon de encerramento, `;` .</span><span class="sxs-lookup"><span data-stu-id="fca32-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="fca32-143">Declarações e declarações como `for` e `operation` que terminam com um bloco de declaração (ver secção seguinte) não requerem um ponto de terminação.</span><span class="sxs-lookup"><span data-stu-id="fca32-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="fca32-144">Cada descrição da declaração observa se o ponto de terminação é necessário.</span><span class="sxs-lookup"><span data-stu-id="fca32-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="fca32-145">Declarações, como expressões, declarações e diretivas, podem ser divididas em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="fca32-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="fca32-146">Evite colocar várias declarações numa única linha.</span><span class="sxs-lookup"><span data-stu-id="fca32-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="fca32-147">Blocos de Declaração</span><span class="sxs-lookup"><span data-stu-id="fca32-147">Statement Blocks</span></span>

<span data-ttu-id="fca32-148">Q#as declarações são agrupadas em blocos de declaração, que são contidos com aparelhos `{ }` .</span><span class="sxs-lookup"><span data-stu-id="fca32-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="fca32-149">Um bloco de declaração começa com uma abertura `{` e termina com um fecho `}` .</span><span class="sxs-lookup"><span data-stu-id="fca32-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="fca32-150">Um bloco de declaração que seja lexicamente fechado dentro de outro bloco é considerado um sub-bloco do bloco contendo; contendo e sub-blocos também são chamados blocos exteriores e internos.</span><span class="sxs-lookup"><span data-stu-id="fca32-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="fca32-151">Comentários</span><span class="sxs-lookup"><span data-stu-id="fca32-151">Comments</span></span>

<span data-ttu-id="fca32-152">Os comentários começam com dois cortes para a `//` frente, e continuam até ao fim da linha.</span><span class="sxs-lookup"><span data-stu-id="fca32-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="fca32-153">Um comentário pode aparecer em qualquer lugar de um Q# ficheiro de origem.</span><span class="sxs-lookup"><span data-stu-id="fca32-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="fca32-154">Comentários de documentação</span><span class="sxs-lookup"><span data-stu-id="fca32-154">Documentation Comments</span></span>

<span data-ttu-id="fca32-155">Comentários que começam com três cortes dianteiros, `///` são tratados especialmente pelo compilador quando aparecem imediatamente antes de um espaço de nome, operação, especialização, função ou definição de tipo.</span><span class="sxs-lookup"><span data-stu-id="fca32-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="fca32-156">Nesse caso, o compilador trata-os como documentação para o tipo definido de calável ou definido pelo utilizador, o mesmo que outras línguas .NET.</span><span class="sxs-lookup"><span data-stu-id="fca32-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="fca32-157">Dentro `///` dos comentários, o texto a aparecer como parte da documentação da API é formatado como [Markdown,](https://daringfireball.net/projects/markdown/syntax)com diferentes partes da documentação indicada por cabeçalhos especialmente nomeados.</span><span class="sxs-lookup"><span data-stu-id="fca32-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="fca32-158">Em Markdown, utilize a `@"<ref target>"` extensão para operações de referência cruzada, funções e tipos definidos pelo utilizador em Q# .</span><span class="sxs-lookup"><span data-stu-id="fca32-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="fca32-159">`<ref target>`Substitua-o pelo nome totalmente qualificado do objeto de código referenciado.</span><span class="sxs-lookup"><span data-stu-id="fca32-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="fca32-160">Diferentes motores de documentação também podem suportar extensões adicionais de Markdown.</span><span class="sxs-lookup"><span data-stu-id="fca32-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="fca32-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fca32-161">For example:</span></span>

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

<span data-ttu-id="fca32-162">Os seguintes nomes são válidos como cabeçalhos de comentário de documentação.</span><span class="sxs-lookup"><span data-stu-id="fca32-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="fca32-163">**Resumo**: Um breve resumo do comportamento de uma função ou funcionamento, ou o propósito de um tipo.</span><span class="sxs-lookup"><span data-stu-id="fca32-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="fca32-164">O primeiro parágrafo do resumo é utilizado para informações sobre hover.</span><span class="sxs-lookup"><span data-stu-id="fca32-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="fca32-165">Deve ser um texto simples.</span><span class="sxs-lookup"><span data-stu-id="fca32-165">It should be plain text.</span></span>
- <span data-ttu-id="fca32-166">**Descrição:** Descrição do comportamento de uma função ou operação, ou o propósito de um tipo.</span><span class="sxs-lookup"><span data-stu-id="fca32-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="fca32-167">Em conjunto, o resumo e descrição formam o ficheiro de documentação gerada para a função, operação ou tipo.</span><span class="sxs-lookup"><span data-stu-id="fca32-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="fca32-168">A descrição suporta símbolos e equações formatados em linha laTeX.</span><span class="sxs-lookup"><span data-stu-id="fca32-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="fca32-169">**Entrada**: Descrição do tuple de entrada para uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="fca32-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="fca32-170">Pode conter subsecções de markdown adicionais que indicam cada elemento do tuple de entrada.</span><span class="sxs-lookup"><span data-stu-id="fca32-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="fca32-171">**Saída**: Descrição do tuple devolvido por uma operação ou função.</span><span class="sxs-lookup"><span data-stu-id="fca32-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="fca32-172">**Parâmetros do tipo**: Secção vazia que contém uma subsecção adicional para cada parâmetro genérico do tipo.</span><span class="sxs-lookup"><span data-stu-id="fca32-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="fca32-173">**Exemplo:** Um pequeno exemplo do funcionamento, função ou tipo de utilização.</span><span class="sxs-lookup"><span data-stu-id="fca32-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="fca32-174">**Observações**: Prosa diversa descrevendo algum aspeto da operação, função ou tipo.</span><span class="sxs-lookup"><span data-stu-id="fca32-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="fca32-175">**Consulte também:** Uma lista de nomes totalmente qualificados que indiquem funções, operações ou tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="fca32-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="fca32-176">**Referências**: Uma lista de referências e citações para o item documentado.</span><span class="sxs-lookup"><span data-stu-id="fca32-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fca32-177">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="fca32-177">Next steps</span></span>

<span data-ttu-id="fca32-178">Conheça as [Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions) em Q# .</span><span class="sxs-lookup"><span data-stu-id="fca32-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>