---
title: Estrutura de arquivos | Microsoft Docs
description: 'Estrutura de arquivos de Q #'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 40b2e7ddf5def6285250dffe130b152429dce1f8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185193"
---
# <a name="file-structure"></a><span data-ttu-id="531fe-103">Estrutura de Ficheiros</span><span class="sxs-lookup"><span data-stu-id="531fe-103">File Structure</span></span>

<span data-ttu-id="531fe-104">Um arquivo Q # consiste em uma sequência de declarações de namespace.</span><span class="sxs-lookup"><span data-stu-id="531fe-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="531fe-105">Cada declaração de namespace contém declarações para tipos, operações e funções definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="531fe-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="531fe-106">Uma declaração de namespace pode conter qualquer número de cada tipo de declaração e em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="531fe-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="531fe-107">O único texto que pode aparecer fora de uma declaração de namespace é comments.</span><span class="sxs-lookup"><span data-stu-id="531fe-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="531fe-108">Em particular, comentários de documentação para um namespace precedem a declaração.</span><span class="sxs-lookup"><span data-stu-id="531fe-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="531fe-109">Declarações de namespace</span><span class="sxs-lookup"><span data-stu-id="531fe-109">Namespace Declarations</span></span>

<span data-ttu-id="531fe-110">Um arquivo Q # normalmente terá exatamente uma declaração de namespace, mas pode ter nenhum (e estar vazio ou apenas conter comentários) ou pode conter vários namespaces.</span><span class="sxs-lookup"><span data-stu-id="531fe-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="531fe-111">Declarações de namespace não podem ser aninhadas.</span><span class="sxs-lookup"><span data-stu-id="531fe-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="531fe-112">O mesmo namespace pode ser declarado em vários arquivos Q # que são compilados juntos, desde que não haja nenhuma declaração de tipo, operação ou função com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="531fe-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="531fe-113">Em particular, é inválido definir o mesmo tipo no mesmo namespace em vários arquivos, mesmo que as declarações sejam idênticas.</span><span class="sxs-lookup"><span data-stu-id="531fe-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="531fe-114">Uma declaração de namespace consiste na `namespace`de palavras-chave, seguida pelo nome do namespace, uma chave de abertura `{`, as declarações contidas no namespace e uma chave de fechamento `}`.</span><span class="sxs-lookup"><span data-stu-id="531fe-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="531fe-115">Os nomes de namespace seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por pontos `.`.</span><span class="sxs-lookup"><span data-stu-id="531fe-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="531fe-116">Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Canon` são nomes de namespace válidos.</span><span class="sxs-lookup"><span data-stu-id="531fe-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="531fe-117">Por convenção, os símbolos em um nome de namespace estão em letras maiúsculas, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="531fe-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="531fe-118">Declarações podem aparecer em qualquer ordem em uma declaração de namespace.</span><span class="sxs-lookup"><span data-stu-id="531fe-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="531fe-119">Referências a tipos ou chamadores declarados mais abaixo em um arquivo são resolvidos corretamente; Não há necessidade de tipo, operação ou declaração de função para preceder uma referência a ele.</span><span class="sxs-lookup"><span data-stu-id="531fe-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="531fe-120">Abrir diretivas</span><span class="sxs-lookup"><span data-stu-id="531fe-120">Open Directives</span></span>

<span data-ttu-id="531fe-121">Dentro de um bloco de namespace, a diretiva `open` pode ser usada para importar todos os tipos e callables definidos em um determinado namespace e consultá-los por seu nome não qualificado.</span><span class="sxs-lookup"><span data-stu-id="531fe-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="531fe-122">Essa diretiva de `open` consiste na palavra-chave `open`, seguida pelo namespace a ser aberto e um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="531fe-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="531fe-123">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="531fe-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="531fe-124">Opcionalmente, um nome curto para o namespace aberto pode ser definido de modo que todos os elementos desse namespace possam (e precisam) ser qualificados pelo nome curto definido.</span><span class="sxs-lookup"><span data-stu-id="531fe-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="531fe-125">Esse nome curto é definido pela adição da palavra-chave `as` seguida pelo nome curto desejado antes do ponto e vírgula em uma diretiva de `open`:</span><span class="sxs-lookup"><span data-stu-id="531fe-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="531fe-126">Todas as diretivas de `open` devem aparecer antes de qualquer `function`, `operation`ou declarações de `newtype` no bloco de namespace.</span><span class="sxs-lookup"><span data-stu-id="531fe-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="531fe-127">A diretiva `open` se aplica ao bloco de namespace inteiro em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="531fe-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="531fe-128">Declarações de tipo definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="531fe-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="531fe-129">O Q # fornece uma maneira para os usuários declararem novos tipos definidos pelo usuário, conforme descrito na seção [modelo do tipo Q #](xref:microsoft.quantum.language.type-model) .</span><span class="sxs-lookup"><span data-stu-id="531fe-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="531fe-130">Os tipos definidos pelo usuário são distintos mesmo se os tipos base forem idênticos.</span><span class="sxs-lookup"><span data-stu-id="531fe-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="531fe-131">Em particular, não há conversão automática entre valores de dois tipos definidos pelo usuário, mesmo que os tipos subjacentes sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="531fe-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="531fe-132">Uma declaração de tipo definida pelo usuário consiste na palavra-chave `newtype`, seguida pelo nome do tipo definido pelo usuário, uma `=`, uma especificação de tipo válida e um ponto e vírgula de terminação.</span><span class="sxs-lookup"><span data-stu-id="531fe-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="531fe-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="531fe-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="531fe-134">Cada arquivo de origem Q # pode declarar qualquer número de tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="531fe-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="531fe-135">Os nomes de tipo devem ser exclusivos em um namespace e podem não entrar em conflito com os nomes de operação e de função.</span><span class="sxs-lookup"><span data-stu-id="531fe-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="531fe-136">Não é possível definir dependências circulares entre tipos definidos pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="531fe-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="531fe-137">Os tipos recursivos, portanto, não são possíveis em Q #.</span><span class="sxs-lookup"><span data-stu-id="531fe-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="531fe-138">Declarações de operação</span><span class="sxs-lookup"><span data-stu-id="531fe-138">Operation Declarations</span></span>

<span data-ttu-id="531fe-139">As operações são o núcleo de Q #, aproximadamente análogo a funções em outras linguagens.</span><span class="sxs-lookup"><span data-stu-id="531fe-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="531fe-140">Cada arquivo de origem Q # pode definir qualquer número de operações.</span><span class="sxs-lookup"><span data-stu-id="531fe-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="531fe-141">Os nomes de operação devem ser exclusivos em um namespace e podem não entrar em conflito com os nomes de tipo e função.</span><span class="sxs-lookup"><span data-stu-id="531fe-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="531fe-142">Uma declaração de operação consiste na `operation`de palavras-chave, seguida pelo símbolo que é o nome da operação, uma tupla de identificador tipada que define os argumentos para a operação, dois pontos `:`, uma anotação de tipo que descreve o tipo de resultado da operação, Opcionalmente, uma anotação com as características da operação, uma chave de abertura `{`, o corpo da declaração da operação e uma chave de fechamento final `}`.</span><span class="sxs-lookup"><span data-stu-id="531fe-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="531fe-143">O corpo da declaração da operação consiste na implementação padrão ou de uma lista de especializações.</span><span class="sxs-lookup"><span data-stu-id="531fe-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="531fe-144">A implementação padrão pode ser especificada diretamente dentro da declaração se apenas a implementação da especialização de corpo padrão precisar especificar explicitamente.</span><span class="sxs-lookup"><span data-stu-id="531fe-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="531fe-145">Nesse caso, uma anotação com as características da operação na declaração é útil para garantir que o compilador gere automaticamente outras especializações com base na implementação padrão.</span><span class="sxs-lookup"><span data-stu-id="531fe-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="531fe-146">Por exemplo</span><span class="sxs-lookup"><span data-stu-id="531fe-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="531fe-147">As características da operação definem quais tipos de transmissão functors podem ser aplicados à operação declarada e qual efeito eles têm.</span><span class="sxs-lookup"><span data-stu-id="531fe-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="531fe-148">Se uma operação implementar uma transformação unitário, será possível definir como a operação age quando *adjointed* ou *controlada*.</span><span class="sxs-lookup"><span data-stu-id="531fe-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="531fe-149">A existência dessas especializações pode ser declarada como parte da assinatura da operação.</span><span class="sxs-lookup"><span data-stu-id="531fe-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="531fe-150">A implementação correspondente para cada tal especialização declarada implicitamente é gerada pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="531fe-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="531fe-151">No exemplo acima, um adjacente, um controlado e uma especialização de adjacente controlada são gerados pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="531fe-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="531fe-152">No caso em que a implementação não pode ser gerada pelo compilador, ela pode ser especificada explicitamente.</span><span class="sxs-lookup"><span data-stu-id="531fe-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="531fe-153">Essas declarações de especialização explícitas podem consistir em uma diretiva de geração adequada que esclareça como uma determinada especialização deve ser criada ou uma implementação definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="531fe-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="531fe-154">O código em `PrepareEntangledPair` acima, por exemplo, é equivalente ao código abaixo que contém declarações de especialização explícitas:</span><span class="sxs-lookup"><span data-stu-id="531fe-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="531fe-155">A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação de especialização.</span><span class="sxs-lookup"><span data-stu-id="531fe-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="531fe-156">Se o compilador não puder gerar a implementação para uma determinada especialização sem mais instruções, como uma diretiva de geração mais precisa, ou se uma implementação mais eficiente puder ser fornecida, a implementação também poderá ser definida manualmente.</span><span class="sxs-lookup"><span data-stu-id="531fe-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

<span data-ttu-id="531fe-157">No exemplo acima, `adjoint invert;` indica que a especialização de adjacente deve ser gerada ao inverter a implementação do corpo e `controlled adjoint invert;` indica que a especialização adjacente controlada deve ser gerada por meio da inversão da implementação fornecida do especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="531fe-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="531fe-158">Para uma operação para dar suporte ao aplicativo do `Adjoint` e/ou `Controlled` functor, seu tipo de retorno precisa ser `Unit`.</span><span class="sxs-lookup"><span data-stu-id="531fe-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="531fe-159">Declarações de especialização explícitas</span><span class="sxs-lookup"><span data-stu-id="531fe-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="531fe-160">As operações de Q # podem conter as seguintes declarações de especialização explícitas:</span><span class="sxs-lookup"><span data-stu-id="531fe-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="531fe-161">A especialização de `body` especifica a implementação da operação sem nenhum transmissão functors aplicado.</span><span class="sxs-lookup"><span data-stu-id="531fe-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="531fe-162">A especialização de `adjoint` especifica a implementação da operação com o `Adjoint` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="531fe-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="531fe-163">A especialização de `controlled` especifica a implementação da operação com o `Controlled` functor aplicado.</span><span class="sxs-lookup"><span data-stu-id="531fe-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="531fe-164">A especialização de `controlled adjoint` especifica a implementação da operação com o `Adjoint` e `Controlled` transmissão functors aplicados.</span><span class="sxs-lookup"><span data-stu-id="531fe-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="531fe-165">Essa especialização também pode ser nomeada `adjoint controlled`, já que as duas transmissão functorsm.</span><span class="sxs-lookup"><span data-stu-id="531fe-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="531fe-166">Uma especialização de operação consiste na marca de especialização (como por exemplo, `body`ou `adjoint`, etc.) seguida de uma das:</span><span class="sxs-lookup"><span data-stu-id="531fe-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="531fe-167">Uma declaração explícita, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="531fe-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="531fe-168">Uma diretiva que informa ao compilador como gerar a especialização, uma das:</span><span class="sxs-lookup"><span data-stu-id="531fe-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="531fe-169">`intrinsic`, que indica que a especialização é fornecida pelo computador de destino.</span><span class="sxs-lookup"><span data-stu-id="531fe-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="531fe-170">`distribute`, que pode ser usado com as especializações `controlled` e `controlled adjoint`.</span><span class="sxs-lookup"><span data-stu-id="531fe-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="531fe-171">Quando usado com `controlled`, ele indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações no `body`.</span><span class="sxs-lookup"><span data-stu-id="531fe-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="531fe-172">Quando usado com `controlled adjoint`, ele indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações na especialização de `adjoint`.</span><span class="sxs-lookup"><span data-stu-id="531fe-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="531fe-173">`invert`, que indica que o compilador deve calcular a especialização de `adjoint` invertendo a `body`, ou seja, revertendo a ordem das operações e aplicando o adjacente a cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="531fe-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="531fe-174">Quando usado com `adjoint controlled`, isso indica que o compilador deve calcular a especialização invertendo a especialização de `controlled`.</span><span class="sxs-lookup"><span data-stu-id="531fe-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="531fe-175">`self`, para indicar que a especialização de adjacente é a mesma que a especialização de `body`.</span><span class="sxs-lookup"><span data-stu-id="531fe-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="531fe-176">Isso é válido para as especialidades de `adjoint` e `adjoint controlled`.</span><span class="sxs-lookup"><span data-stu-id="531fe-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="531fe-177">Por `adjoint controlled`, `self` implica que a especialização de `adjoint controlled` é a mesma que a especialização de `controlled`.</span><span class="sxs-lookup"><span data-stu-id="531fe-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="531fe-178">`auto`, para indicar que o compilador deve selecionar uma diretiva apropriada a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="531fe-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="531fe-179">`auto` não pode ser usado para a especialização de `body`.</span><span class="sxs-lookup"><span data-stu-id="531fe-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="531fe-180">As diretivas e `auto` todos exigem um ponto-e-`;`vírgula de fechamento.</span><span class="sxs-lookup"><span data-stu-id="531fe-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="531fe-181">A diretiva `auto` é resolvida para a seguinte diretiva de geração se uma declaração explícita da `body` for fornecida:</span><span class="sxs-lookup"><span data-stu-id="531fe-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="531fe-182">A especialização de `adjoint` é gerada de acordo com a diretiva `invert`.</span><span class="sxs-lookup"><span data-stu-id="531fe-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="531fe-183">A especialização de `controlled` é gerada de acordo com a diretiva `distribute`.</span><span class="sxs-lookup"><span data-stu-id="531fe-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="531fe-184">A especialização de `adjoint controlled` é gerada de acordo com a diretiva `invert` se uma declaração explícita para `controlled` for fornecida, mas não uma para `adjoint`e `distribute` caso contrário.</span><span class="sxs-lookup"><span data-stu-id="531fe-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="531fe-185">Se uma operação for autoadjacente, especifique explicitamente a prejunção ou a especialização de adjacente controlada por meio da diretiva de geração `self` para permitir que o compilador use essas informações para fins de otimização.</span><span class="sxs-lookup"><span data-stu-id="531fe-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="531fe-186">Uma declaração de especialização contendo uma implementação definida pelo usuário consiste em uma tupla de argumento seguida por um bloco de instrução com o código Q # que implementa a especialização.</span><span class="sxs-lookup"><span data-stu-id="531fe-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="531fe-187">Na lista de argumentos, `...` é usado para representar os argumentos declarados para a operação como um todo.</span><span class="sxs-lookup"><span data-stu-id="531fe-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="531fe-188">Para `body` e `adjoint`, a lista de argumentos sempre deve ser `(...)`; para `controlled` e `adjoint controlled`, a lista de argumentos deve ser um símbolo que representa a matriz de qubits de controle, seguida por `...`, entre parênteses; por exemplo, `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="531fe-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="531fe-189">Se uma ou mais especializações além do corpo padrão precisarem ser declaradas explicitamente, a implementação do corpo padrão precisará ser encapsulada em uma declaração de especialização adequada também:</span><span class="sxs-lookup"><span data-stu-id="531fe-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qs: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (q in qs) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="531fe-190">Adjacente</span><span class="sxs-lookup"><span data-stu-id="531fe-190">Adjoint</span></span>

<span data-ttu-id="531fe-191">O erro de uma operação especifica como a seqüência conjugada complexa da operação é implementada, ou seja, como a operação atua quando "executar em ordem inversa".</span><span class="sxs-lookup"><span data-stu-id="531fe-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="531fe-192">É legal especificar uma operação sem nenhum erro; por exemplo, as operações de medição não têm nenhum adjacente porque não são invertível.</span><span class="sxs-lookup"><span data-stu-id="531fe-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="531fe-193">Uma operação dá suporte ao `Adjoint` functor se sua declaração contiver uma declaração implícita ou explícita de uma especialização adjacente.</span><span class="sxs-lookup"><span data-stu-id="531fe-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="531fe-194">Uma especialização adjacente controlada explicitamente implica a existência de uma especialização adjacente.</span><span class="sxs-lookup"><span data-stu-id="531fe-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="531fe-195">Para a operação cujo corpo contém loops repetir-até-êxito, instruções SET, medidas, instruções de retorno ou chamadas para outras operações que não dão suporte ao `Adjoint` functor, gerando automaticamente uma especialização de adjacente após a `invert` ou @no__ a diretiva t_2_ não é possível.</span><span class="sxs-lookup"><span data-stu-id="531fe-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="531fe-196">Controlado</span><span class="sxs-lookup"><span data-stu-id="531fe-196">Controlled</span></span>

<span data-ttu-id="531fe-197">A versão controlada de uma operação especifica como uma versão controlada pelo Quantum da operação é implementada, ou seja, como uma operação age quando aplicada no estado de um registro Quantum.</span><span class="sxs-lookup"><span data-stu-id="531fe-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="531fe-198">Uma descrição mais completa é fornecida na seção [controlada](xref:microsoft.quantum.language.type-model#controlled) .</span><span class="sxs-lookup"><span data-stu-id="531fe-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="531fe-199">É legal especificar uma operação sem nenhuma versão controlada; por exemplo, as operações de medição não têm nenhuma versão controlada porque não são controláveis.</span><span class="sxs-lookup"><span data-stu-id="531fe-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="531fe-200">Uma operação dá suporte ao `Controlled` functor se e somente se sua declaração contiver uma declaração implícita ou explícita de uma especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="531fe-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="531fe-201">Uma especialização adjacente controlada explicitamente implica a existência de uma especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="531fe-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="531fe-202">Para uma operação cujo corpo contém chamadas para outras operações que não dão suporte ao `Controlled` functor, a geração automática de uma especialização controlada seguindo a diretiva `distribute` ou `auto` não é possível.</span><span class="sxs-lookup"><span data-stu-id="531fe-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="531fe-203">Adjacente controlado</span><span class="sxs-lookup"><span data-stu-id="531fe-203">Controlled Adjoint</span></span>

<span data-ttu-id="531fe-204">A versão adjacente controlada de uma operação especifica como uma versão controlada pelo Quantum do adjoin da operação é implementada.</span><span class="sxs-lookup"><span data-stu-id="531fe-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="531fe-205">É legal especificar uma operação sem nenhuma versão adjacente controlada; por exemplo, as operações de medição não têm nenhuma versão adjacente controlada porque não são controláveis nem invertível.</span><span class="sxs-lookup"><span data-stu-id="531fe-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="531fe-206">Uma especialização de adjacente controlada para uma operação precisa existir se e somente se houver uma especialização de somente um e um adjacente.</span><span class="sxs-lookup"><span data-stu-id="531fe-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="531fe-207">Nesse caso, a existência da especialização adjacente controlada é inferida e uma especialização apropriada é gerada pelo compilador se nenhuma implementação tiver sido definida explicitamente.</span><span class="sxs-lookup"><span data-stu-id="531fe-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="531fe-208">Para uma operação cujo corpo contém chamadas para outras operações que não têm uma versão adjacente controlada, a geração automática de uma especialização de adjacente após o `invert`, `distribute` ou diretiva de `auto` não é possível.</span><span class="sxs-lookup"><span data-stu-id="531fe-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="531fe-209">Exemplos</span><span class="sxs-lookup"><span data-stu-id="531fe-209">Examples</span></span>

<span data-ttu-id="531fe-210">Uma declaração de operação pode ser tão simples quanto a seguinte, que define a operação primitiva de Pauli X:</span><span class="sxs-lookup"><span data-stu-id="531fe-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (q : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="531fe-211">O seguinte define a operação teleport.</span><span class="sxs-lookup"><span data-stu-id="531fe-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="531fe-212">Declarações de função</span><span class="sxs-lookup"><span data-stu-id="531fe-212">Function Declarations</span></span>

<span data-ttu-id="531fe-213">São rotinas puramente clássicas em Q #.</span><span class="sxs-lookup"><span data-stu-id="531fe-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="531fe-214">Cada arquivo de origem Q # pode definir qualquer número de funções.</span><span class="sxs-lookup"><span data-stu-id="531fe-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="531fe-215">Uma declaração de função consiste na `function`de palavras-chave, seguida pelo símbolo que é o nome da função, uma tupla de identificador tipada, uma anotação de tipo que descreve o tipo de retorno da função e um bloco de instruções que descreve a implementação do funcionamento.</span><span class="sxs-lookup"><span data-stu-id="531fe-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="531fe-216">O bloco de instrução que define uma função deve ser colocado entre `{` e `}` como qualquer outro bloco de instrução.</span><span class="sxs-lookup"><span data-stu-id="531fe-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="531fe-217">Os nomes de função devem ser exclusivos em um namespace e podem não entrar em conflito com os nomes de operação e tipo.</span><span class="sxs-lookup"><span data-stu-id="531fe-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="531fe-218">As funções podem não alocar ou emprestar qubits ou chamar operações.</span><span class="sxs-lookup"><span data-stu-id="531fe-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="531fe-219">A aplicação parcial de operações ou a passagem de valores tipados da operação está bem.</span><span class="sxs-lookup"><span data-stu-id="531fe-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="531fe-220">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="531fe-220">For example,</span></span>

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
