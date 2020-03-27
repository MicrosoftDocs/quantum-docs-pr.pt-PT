---
title: Q# Estrutura de Arquivo
description: Saiba como estruturar espaços de nome, e operação, função e declarações de tipo utilizador definidos em programas e bibliotecas Q#.
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 96de062bc6ce4edf94520bec449e8d95259c0f5c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320763"
---
# <a name="file-structure"></a><span data-ttu-id="2d91e-103">Estrutura de Ficheiros</span><span class="sxs-lookup"><span data-stu-id="2d91e-103">File Structure</span></span>

<span data-ttu-id="2d91e-104">Um ficheiro Q# consiste numa sequência de declarações de espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="2d91e-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="2d91e-105">Cada declaração de espaço de nome contém declarações para tipos, operações e funções definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="2d91e-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="2d91e-106">Uma declaração de espaço-nome pode conter qualquer número de cada tipo de declaração, e em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="2d91e-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="2d91e-107">O único texto que pode aparecer fora de uma declaração de espaço de nome são os comentários.</span><span class="sxs-lookup"><span data-stu-id="2d91e-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="2d91e-108">Em particular, os comentários documentais relativos a um espaço de nome precedem a declaração.</span><span class="sxs-lookup"><span data-stu-id="2d91e-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="2d91e-109">Declarações de espaço de nome</span><span class="sxs-lookup"><span data-stu-id="2d91e-109">Namespace Declarations</span></span>

<span data-ttu-id="2d91e-110">Um ficheiro Q# terá normalmente uma declaração de espaço-nome, mas pode ter nenhuma (e estar vazia ou apenas conter comentários) ou pode conter vários espaços de nome.</span><span class="sxs-lookup"><span data-stu-id="2d91e-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="2d91e-111">As declarações de espaço-nome não podem ser aninhadas.</span><span class="sxs-lookup"><span data-stu-id="2d91e-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="2d91e-112">O mesmo espaço de nome pode ser declarado em vários ficheiros Q# que são compilados em conjunto, desde que não existam declarações de tipo, operação ou função com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="2d91e-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="2d91e-113">Em particular, é inválido definir o mesmo tipo no mesmo espaço de nome em vários ficheiros, mesmo que as declarações sejam idênticas.</span><span class="sxs-lookup"><span data-stu-id="2d91e-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="2d91e-114">Uma declaração de espaço de nome consiste na palavra-chave `namespace`, seguida do nome do espaço de nome, de um `{`de cinta aberta, das declarações contidas no espaço de nome, e de um `}`de cinta estreita .</span><span class="sxs-lookup"><span data-stu-id="2d91e-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="2d91e-115">Os nomes do espaço de nome seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por períodos `.`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="2d91e-116">Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Canon` são nomes de espaço de nome válidos.</span><span class="sxs-lookup"><span data-stu-id="2d91e-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="2d91e-117">Por convenção, os símbolos de um nome de espaço de nome são capitalizados, mas isso não é necessário.</span><span class="sxs-lookup"><span data-stu-id="2d91e-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="2d91e-118">As declarações podem aparecer em qualquer ordem numa declaração de espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="2d91e-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="2d91e-119">As referências a tipos ou callables declarados mais abaixo num ficheiro são devidamente resolvidas; não há necessidade de o tipo, operação ou declaração de função preceder uma referência a ele.</span><span class="sxs-lookup"><span data-stu-id="2d91e-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="2d91e-120">Diretivas abertas</span><span class="sxs-lookup"><span data-stu-id="2d91e-120">Open Directives</span></span>

<span data-ttu-id="2d91e-121">Dentro de um bloco de espaço-nome, a diretiva `open` pode ser utilizada para importar todos os tipos e calíveis definidos num determinado espaço de nome e encaminhá-los pelo seu nome não qualificado.</span><span class="sxs-lookup"><span data-stu-id="2d91e-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="2d91e-122">Tal diretiva `open` consiste na palavra-chave `open`, seguida do espaço de nome a abrir e de um ponto evíceo que termina.</span><span class="sxs-lookup"><span data-stu-id="2d91e-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="2d91e-123">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="2d91e-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="2d91e-124">Opcionalmente, pode ser definido um nome curto para o espaço de nome aberto de modo a que todos os elementos desse espaço de nome possam (e precisam) ser qualificados pelo nome curto definido.</span><span class="sxs-lookup"><span data-stu-id="2d91e-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="2d91e-125">Este nome curto é definido adicionando a palavra-chave `as` seguida do nome curto desejado antes do ponto evícito numa diretiva `open`:</span><span class="sxs-lookup"><span data-stu-id="2d91e-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="2d91e-126">Todas as diretivas `open` devem comparecer antes de qualquer `function`, `operation`ou `newtype` declarações no bloco de nomes.</span><span class="sxs-lookup"><span data-stu-id="2d91e-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="2d91e-127">A diretiva `open` aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.</span><span class="sxs-lookup"><span data-stu-id="2d91e-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="2d91e-128">Declarações de tipo definidos pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="2d91e-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="2d91e-129">Q# fornece uma forma de os utilizadores declararem novos tipos definidos pelo utilizador, conforme descrito na secção do [modelo Q#.](xref:microsoft.quantum.language.type-model)</span><span class="sxs-lookup"><span data-stu-id="2d91e-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="2d91e-130">Os tipos definidos pelo utilizador são distintos mesmo que os tipos de base sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="2d91e-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="2d91e-131">Em particular, não existe uma conversão automática entre valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.</span><span class="sxs-lookup"><span data-stu-id="2d91e-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="2d91e-132">Uma declaração de tipo definido pelo utilizador consiste na palavra-chave `newtype`, seguida do nome do tipo definido pelo utilizador, de um `=`, de uma especificação de tipo válido e de um ponto e vírgula terminando.</span><span class="sxs-lookup"><span data-stu-id="2d91e-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="2d91e-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2d91e-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="2d91e-134">Cada ficheiro de origem Q# pode declarar qualquer número de tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="2d91e-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="2d91e-135">Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de funcionamento e função.</span><span class="sxs-lookup"><span data-stu-id="2d91e-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="2d91e-136">Não é possível definir dependências circulares entre tipos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="2d91e-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="2d91e-137">Os tipos recursivos não são assim possíveis dentro do Q#.</span><span class="sxs-lookup"><span data-stu-id="2d91e-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="2d91e-138">Declarações de Operação</span><span class="sxs-lookup"><span data-stu-id="2d91e-138">Operation Declarations</span></span>

<span data-ttu-id="2d91e-139">As operações são o núcleo de Q#, aproximadamente análogo a funções em outras línguas.</span><span class="sxs-lookup"><span data-stu-id="2d91e-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="2d91e-140">Cada ficheiro de origem Q# pode definir qualquer número de operações.</span><span class="sxs-lookup"><span data-stu-id="2d91e-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="2d91e-141">Os nomes de funcionamento devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de tipo e função.</span><span class="sxs-lookup"><span data-stu-id="2d91e-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="2d91e-142">Uma declaração de operação consiste na palavra-chave `operation`, seguida do símbolo que é o nome da operação, de uma túnica de identificador dactilografada que define os argumentos da operação, de um cólon `:`, de uma anotação tipo que descreve o tipo de resultado da operação, opcionalmente uma anotação com as características de funcionamento, uma braçadeira aberta `{`, o corpo da declaração de operação e um `}`final de fecho.</span><span class="sxs-lookup"><span data-stu-id="2d91e-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="2d91e-143">O corpo da declaração de operação consiste na implementação por defeito ou numa lista de especializações.</span><span class="sxs-lookup"><span data-stu-id="2d91e-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="2d91e-144">A implementação por defeito pode ser especificada diretamente na declaração se apenas a implementação da especialização do corpo padrão precisar especificar explicitamente.</span><span class="sxs-lookup"><span data-stu-id="2d91e-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="2d91e-145">Neste caso, uma anotação com as características de funcionamento na declaração é útil para garantir que o compilador gera automaticamente outras especializações com base na implementação padrão.</span><span class="sxs-lookup"><span data-stu-id="2d91e-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="2d91e-146">Por exemplo</span><span class="sxs-lookup"><span data-stu-id="2d91e-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="2d91e-147">As características de funcionamento definem que tipos de functores podem ser aplicados à operação declarada e que efeito têm.</span><span class="sxs-lookup"><span data-stu-id="2d91e-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="2d91e-148">Se uma operação implementar uma transformação unitária, então é possível definir como a operação funciona quando *adjoint ou* *controlada*.</span><span class="sxs-lookup"><span data-stu-id="2d91e-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="2d91e-149">A existência destas especializações pode ser declarada como parte da assinatura da operação.</span><span class="sxs-lookup"><span data-stu-id="2d91e-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="2d91e-150">A implementação correspondente para cada especialização declarada implicitamente é então gerada pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="2d91e-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="2d91e-151">No exemplo acima, um adjoint, um controlado e uma especialização adjoint controlada são gerados pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="2d91e-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="2d91e-152">No caso de a implementação não poder ser gerada pelo compilador, pode ser explicitamente especificada.</span><span class="sxs-lookup"><span data-stu-id="2d91e-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="2d91e-153">Tais declarações explícitas de especialização podem consistir numa diretiva de geração adequada que clarifique a forma como uma determinada especialização deve ser construída, ou uma implementação definida pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="2d91e-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="2d91e-154">O código em `PrepareEntangledPair` acima, por exemplo, equivale ao código abaixo contendo declarações explícitas de especialização:</span><span class="sxs-lookup"><span data-stu-id="2d91e-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="2d91e-155">A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação da especialização.</span><span class="sxs-lookup"><span data-stu-id="2d91e-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="2d91e-156">Se o compilador não conseguir gerar a implementação de uma determinada especialização sem instruções adicionais - como uma diretiva de geração mais precisa - ou se uma implementação mais eficiente puder ser administrada, então a implementação também pode ser definida manualmente.</span><span class="sxs-lookup"><span data-stu-id="2d91e-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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

<span data-ttu-id="2d91e-157">No exemplo acima, `adjoint invert;` indica que a especialização adjoint deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjoint controlada deve ser gerada invertendo a implementação da especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="2d91e-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="2d91e-158">Para uma operação de apoio à aplicação do functor `Adjoint` e/ou `Controlled`, o seu tipo de retorno precisa necessariamente de ser `Unit`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="2d91e-159">Declarações explícitas de especialização</span><span class="sxs-lookup"><span data-stu-id="2d91e-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="2d91e-160">Q# as operações podem conter as seguintes declarações explícitas de especialização:</span><span class="sxs-lookup"><span data-stu-id="2d91e-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="2d91e-161">A `body` especialização especifica a implementação da operação sem functores aplicados.</span><span class="sxs-lookup"><span data-stu-id="2d91e-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="2d91e-162">A `adjoint` especialização especifica a implementação da operação com o functor `Adjoint` aplicado.</span><span class="sxs-lookup"><span data-stu-id="2d91e-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="2d91e-163">A `controlled` especialização especifica a implementação da operação com o functor `Controlled` aplicado.</span><span class="sxs-lookup"><span data-stu-id="2d91e-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="2d91e-164">A `controlled adjoint` especialização especifica a implementação da operação com os functores `Adjoint` e `Controlled` aplicados.</span><span class="sxs-lookup"><span data-stu-id="2d91e-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="2d91e-165">Esta especialização também pode ser nomeada `adjoint controlled`, uma vez que os dois functors viajam.</span><span class="sxs-lookup"><span data-stu-id="2d91e-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="2d91e-166">Uma especialização de operação consiste na etiqueta de especialização (como, por exemplo, `body`, ou `adjoint`, etc.) seguida de uma das:</span><span class="sxs-lookup"><span data-stu-id="2d91e-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="2d91e-167">Uma declaração explícita, como descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="2d91e-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="2d91e-168">Uma diretiva que diz ao compilador como gerar a especialização, uma das:</span><span class="sxs-lookup"><span data-stu-id="2d91e-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="2d91e-169">`intrinsic`, o que indica que a especialização é fornecida pela máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="2d91e-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="2d91e-170">`distribute`, que podem ser utilizados com as especialidades `controlled` e `controlled adjoint`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="2d91e-171">Quando utilizado com `controlled`, indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações do `body`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="2d91e-172">Quando utilizado com `controlled adjoint`, indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações na `adjoint` especialização.</span><span class="sxs-lookup"><span data-stu-id="2d91e-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="2d91e-173">`invert`, que indica que o compilador deve calcular a `adjoint` especialização invertendo a `body`, ou seja, inverter a ordem de operações e aplicar o adjoint a cada um.</span><span class="sxs-lookup"><span data-stu-id="2d91e-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="2d91e-174">Quando utilizado com `adjoint controlled`, isto indica que o compilador deve calcular a especialização invertendo a `controlled` especialização.</span><span class="sxs-lookup"><span data-stu-id="2d91e-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="2d91e-175">`self`, para indicar que a especialização adjoint é a mesma que a `body` especialização.</span><span class="sxs-lookup"><span data-stu-id="2d91e-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="2d91e-176">Isto é legal para as `adjoint` e `adjoint controlled` especializações.</span><span class="sxs-lookup"><span data-stu-id="2d91e-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="2d91e-177">Para `adjoint controlled`, `self` implica que a `adjoint controlled` especialização é a mesma que a `controlled` especialização.</span><span class="sxs-lookup"><span data-stu-id="2d91e-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="2d91e-178">`auto`, para indicar que o compilador deve selecionar uma diretiva adequada a aplicar.</span><span class="sxs-lookup"><span data-stu-id="2d91e-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="2d91e-179">`auto` não pode ser utilizado para a especialização `body`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="2d91e-180">As diretivas e `auto` todos exigem um `;`de fecho do ponto-de-meia-cólon.</span><span class="sxs-lookup"><span data-stu-id="2d91e-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="2d91e-181">A diretiva `auto` resolve-se com a seguinte diretiva de geração se for fornecida uma declaração explícita do `body`:</span><span class="sxs-lookup"><span data-stu-id="2d91e-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="2d91e-182">A `adjoint` especialização é gerada de acordo com a diretiva `invert`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="2d91e-183">A `controlled` especialização é gerada de acordo com a diretiva `distribute`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="2d91e-184">A `adjoint controlled` especialização é gerada de acordo com a diretiva `invert` se for dada uma declaração explícita para `controlled`, mas não para `adjoint`, e `distribute` o contrário.</span><span class="sxs-lookup"><span data-stu-id="2d91e-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="2d91e-185">Se uma operação for auto-adjoint, especifique explicitamente a adjoint ou a especialização adjoint controlada através da diretiva de geração `self` permitir que o compilador utilize essa informação para fins de otimização.</span><span class="sxs-lookup"><span data-stu-id="2d91e-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="2d91e-186">Uma declaração de especialização contendo uma implementação definida pelo utilizador consiste num argumento de tuple seguido de um bloco de declaração com o código Q# que implementa a especialização.</span><span class="sxs-lookup"><span data-stu-id="2d91e-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="2d91e-187">Na lista de argumentos, `...` é usada para representar os argumentos declarados para a operação como um todo.</span><span class="sxs-lookup"><span data-stu-id="2d91e-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="2d91e-188">Para `body` e `adjoint`, a lista de argumentos deve ser sempre `(...)`; Para `controlled` e `adjoint controlled`, a lista de argumentos deve ser um símbolo que represente o conjunto de qubits de controlo, seguidos de `...`, em parênteses; por exemplo, `(controls,...)`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="2d91e-189">Se uma ou mais especializações para além do corpo padrão precisarde matem explicitamente, então a implementação do organismo predefinido deve ser embrulhada numa declaração de especialização adequada:</span><span class="sxs-lookup"><span data-stu-id="2d91e-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a><span data-ttu-id="2d91e-190">Adjoint</span><span class="sxs-lookup"><span data-stu-id="2d91e-190">Adjoint</span></span>

<span data-ttu-id="2d91e-191">O adjoint de uma operação especifica como é implementada a transposição complexa conjugada da operação, ou seja, como funciona a operação quando "corre ao contrário".</span><span class="sxs-lookup"><span data-stu-id="2d91e-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="2d91e-192">É legal especificar uma operação sem adjoint; por exemplo, as operações de medição não têm adjoint porque não são invertáveis.</span><span class="sxs-lookup"><span data-stu-id="2d91e-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="2d91e-193">Uma operação apoia o functor `Adjoint` se a sua declaração contiver uma declaração implícita ou explícita de uma especialização adjoint.</span><span class="sxs-lookup"><span data-stu-id="2d91e-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="2d91e-194">Uma especialização adjoint explicitamente declarada implica a existência de uma especialização adjoint.</span><span class="sxs-lookup"><span data-stu-id="2d91e-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="2d91e-195">Para a operação cujo corpo contenha ciclos de repetição até ao sucesso, definindo declarações, medições, declarações de devolução ou chamadas para outras operações que não suportem o functor `Adjoint`, gerando automaticamente uma especialização adjoint na sequência da diretiva `invert` ou `auto` não é possível.</span><span class="sxs-lookup"><span data-stu-id="2d91e-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="2d91e-196">Controlado</span><span class="sxs-lookup"><span data-stu-id="2d91e-196">Controlled</span></span>

<span data-ttu-id="2d91e-197">A versão controlada de uma operação especifica como é implementada uma versão quântica da operação, ou seja, como uma operação funciona quando aplicada condicionada no estado de um registo quântico.</span><span class="sxs-lookup"><span data-stu-id="2d91e-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="2d91e-198">Uma descrição mais completa é fornecida na secção [Controlada.](xref:microsoft.quantum.language.type-model#controlled)</span><span class="sxs-lookup"><span data-stu-id="2d91e-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="2d91e-199">É legal especificar uma operação sem versão controlada; por exemplo, as operações de medição não têm versão controlada porque não são controláveis.</span><span class="sxs-lookup"><span data-stu-id="2d91e-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="2d91e-200">Uma operação apoia o functor `Controlled` se e apenas se a sua declaração contiver uma declaração implícita ou explícita de uma especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="2d91e-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="2d91e-201">Uma especialização adjoint explicitamente declarada implica a existência de uma especialização controlada.</span><span class="sxs-lookup"><span data-stu-id="2d91e-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="2d91e-202">Para uma operação cujo corpo contenha chamadas para outras operações que não suportem o functor `Controlled`, não é possível gerar automaticamente uma especialização controlada na sequência da diretiva `distribute` ou `auto`.</span><span class="sxs-lookup"><span data-stu-id="2d91e-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="2d91e-203">Adjoint controlado</span><span class="sxs-lookup"><span data-stu-id="2d91e-203">Controlled Adjoint</span></span>

<span data-ttu-id="2d91e-204">A versão adjoint controlada de uma operação especifica como é implementada uma versão quântica da adjoint da operação.</span><span class="sxs-lookup"><span data-stu-id="2d91e-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="2d91e-205">É legal especificar uma operação sem versão adjoint controlada; por exemplo, as operações de medição não têm versão adjoint controlada porque não são controláveis nem invertíveis.</span><span class="sxs-lookup"><span data-stu-id="2d91e-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="2d91e-206">Uma especialização adjoint controlada para uma operação precisa de existir se e apenas se existir uma especialização adjoint e controlada.</span><span class="sxs-lookup"><span data-stu-id="2d91e-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="2d91e-207">Nesse caso, a existência da especialização adjoint controlada é inferida e uma especialização adequada é gerada pelo compilador se não tiver sido definida explicitamente nenhuma implementação.</span><span class="sxs-lookup"><span data-stu-id="2d91e-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="2d91e-208">Para uma operação cujo corpo contenha chamadas para outras operações que não tenham uma versão adjoint controlada, gerando automaticamente uma especialização adjoint na sequência da diretiva `invert`, `distribute` ou `auto` não é possível.</span><span class="sxs-lookup"><span data-stu-id="2d91e-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="2d91e-209">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2d91e-209">Examples</span></span>

<span data-ttu-id="2d91e-210">Uma declaração de operação pode ser tão simples como a seguinte, que define a operação primitiva Pauli X:</span><span class="sxs-lookup"><span data-stu-id="2d91e-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="2d91e-211">O seguinte define a operação do teletransporte.</span><span class="sxs-lookup"><span data-stu-id="2d91e-211">The following defines the teleport operation.</span></span>

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation PrepareEntangledPair (q1 : Qubit, q2 : Qubit) : Unit 
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
        PrepareEntangledPair(target, ancilla);

        // Do the teleportation
        Adjoint PrepareEntangledPair(ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a><span data-ttu-id="2d91e-212">Declarações de Funções</span><span class="sxs-lookup"><span data-stu-id="2d91e-212">Function Declarations</span></span>

<span data-ttu-id="2d91e-213">As funções são rotinas puramente clássicas em Q#.</span><span class="sxs-lookup"><span data-stu-id="2d91e-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="2d91e-214">Cada ficheiro de origem Q# pode definir qualquer número de funções.</span><span class="sxs-lookup"><span data-stu-id="2d91e-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="2d91e-215">Uma declaração de função consiste na palavra-chave `function`, seguida do símbolo que é o nome da função, um túnica identificador dactilografado, uma anotação tipo que descreve o tipo de retorno da função, e um bloco de declaração que descreve a implementação da função.</span><span class="sxs-lookup"><span data-stu-id="2d91e-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="2d91e-216">O bloco de declaração que define uma função deve ser incluído em `{` e `}` como qualquer outro bloco de declaração.</span><span class="sxs-lookup"><span data-stu-id="2d91e-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="2d91e-217">Os nomes de funções devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento e os nomes de tipo.</span><span class="sxs-lookup"><span data-stu-id="2d91e-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="2d91e-218">As funções não podem alocar ou emprestar qubits, ou operações de chamada.</span><span class="sxs-lookup"><span data-stu-id="2d91e-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="2d91e-219">A aplicação parcial das operações ou a passagem em torno dos valores dactilografados de operação é boa.</span><span class="sxs-lookup"><span data-stu-id="2d91e-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="2d91e-220">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="2d91e-220">For example,</span></span>

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


## <a name="internal-declarations"></a><span data-ttu-id="2d91e-221">Declarações Internas</span><span class="sxs-lookup"><span data-stu-id="2d91e-221">Internal Declarations</span></span>

<span data-ttu-id="2d91e-222">Os tipos, operações e funções definidos pelo utilizador também podem ser declarados *internos*.</span><span class="sxs-lookup"><span data-stu-id="2d91e-222">User-defined types, operations, and functions can also be declared as *internal*.</span></span>
<span data-ttu-id="2d91e-223">Isto significa que só podem ser acedidos a partir do âmbito do projeto Q# em que são declarados.</span><span class="sxs-lookup"><span data-stu-id="2d91e-223">This means that they can only be accessed from within the Q# project that they are declared in.</span></span>
<span data-ttu-id="2d91e-224">Quando um projeto é usado como referência, todas as suas declarações *públicas* (não internas) são disponibilizadas, mas tentar utilizar uma declaração interna de outro projeto produzirá um erro.</span><span class="sxs-lookup"><span data-stu-id="2d91e-224">When a project is used as a reference, all of its *public* (non-internal) declarations are made available, but trying to use an internal declaration from another project will produce an error.</span></span>
<span data-ttu-id="2d91e-225">As declarações internas são úteis para escrever código modular que pode ser reutilizado por outras partes do seu projeto, mas ainda assim ser alterado mais tarde sem quebrar outros projetos que possam depender dele.</span><span class="sxs-lookup"><span data-stu-id="2d91e-225">Internal declarations are useful for writing modular code that can be reused by other parts of your project, but still be changed later without breaking other projects that might depend on it.</span></span>

<span data-ttu-id="2d91e-226">Um tipo, funcionamento ou função interno definido pelo utilizador pode ser declarado simplesmente adicionando `internal` no início da declaração.</span><span class="sxs-lookup"><span data-stu-id="2d91e-226">An internal user-defined type, operation, or function can be declared simply by adding `internal` at the beginning of the declaration.</span></span>
<span data-ttu-id="2d91e-227">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="2d91e-227">For example,</span></span>

```qsharp
internal newtype PairOfQubits = (Qubit, Qubit);

internal operation PrepareEntangledPair(pair : PairOfQubits) : Unit 
is Adj + Ctl {
    let (q1, q2) = pair!;
    H(q2);
    CNOT(q2, q1);
}

internal function DotProduct(a : Double[], b : Double[]) : Double {
    ...
}
```

> [!WARNING]
> <span data-ttu-id="2d91e-228">Os tipos internos definidos pelo utilizador só podem ser utilizados em assinaturas ou tipos subjacentes se o tipo correspondente de callable ou definido pelo utilizador também for interno.</span><span class="sxs-lookup"><span data-stu-id="2d91e-228">Internal user-defined types can only be used in signatures or underlying types if the corresponding callable or user-defined type is also internal.</span></span>
> <span data-ttu-id="2d91e-229">Por exemplo, se houver um tipo definido pelo utilizador `InternalOptions` que tenha sido declarado com a palavra-chave `internal`, então as seguintes declarações resultarão em erros:</span><span class="sxs-lookup"><span data-stu-id="2d91e-229">For example, if there is a user-defined type `InternalOptions` that was declared with the `internal` keyword, then the following declarations will result in errors:</span></span>
>
> ```qsharp
> // Error: Can't use InternalOptions as an output type of a public function.
> function DefaultInternalOptions() : InternalOptions { ... }
>
> // Error: Can't use InternalOptions as an item in a public user-defined type.
> newtype ExtendedOptions = (Internal : InternalOptions);
> ```
