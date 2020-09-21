---
title: Q#Guia de estilo da Microsoft
description: Aprenda as convenções de nomeação, entrada, documentação e formatação para Q# programas e bibliotecas.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
no-loc:
- Q#
- $$v
ms.openlocfilehash: fef3cea1c11e4fef49ddbf63adb34e07675049d2
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834198"
---
# <a name="no-locq-style-guide"></a><span data-ttu-id="a77a2-103">Q# Guia de estilo</span><span class="sxs-lookup"><span data-stu-id="a77a2-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="a77a2-104">Convenções Gerais</span><span class="sxs-lookup"><span data-stu-id="a77a2-104">General Conventions</span></span> ##

<span data-ttu-id="a77a2-105">As convenções sugeridas neste guia destinam-se a ajudar a tornar os programas e bibliotecas escritos Q# de forma mais fácil de ler e compreender.</span><span class="sxs-lookup"><span data-stu-id="a77a2-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="a77a2-106">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-106">Guidance</span></span>

<span data-ttu-id="a77a2-107">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-107">We suggest:</span></span>

- <span data-ttu-id="a77a2-108">Nunca ignore uma convenção a menos que o faça intencionalmente para fornecer um código mais legível e compreensível para os seus utilizadores.</span><span class="sxs-lookup"><span data-stu-id="a77a2-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="a77a2-109">Convenções de Nomeação</span><span class="sxs-lookup"><span data-stu-id="a77a2-109">Naming Conventions</span></span> ##

<span data-ttu-id="a77a2-110">Ao oferecermos o Kit de Desenvolvimento Quântico, esforçamo-nos por nomes de funções e de operação que ajudam os desenvolvedores quânticos a escrever programas que são fáceis de ler e que minimizam a surpresa.</span><span class="sxs-lookup"><span data-stu-id="a77a2-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="a77a2-111">Uma parte importante disso é que, quando escolhemos nomes para funções, operações e tipos, estamos a estabelecer o *vocabulário* que os programadores usam para expressar conceitos quânticos; com as nossas escolhas, ou ajudamos ou os dificultamos no seu esforço para comunicar claramente.</span><span class="sxs-lookup"><span data-stu-id="a77a2-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="a77a2-112">Isto coloca-nos a responsabilidade de garantir que os nomes que introduzimos ofereçam clareza em vez de obscuridade.</span><span class="sxs-lookup"><span data-stu-id="a77a2-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="a77a2-113">Nesta secção, detalhamos como cumprimos esta obrigação em termos de orientação explícita que nos ajuda a fazer o melhor pela comunidade de Q# desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="a77a2-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="a77a2-114">Operações e Funções</span><span class="sxs-lookup"><span data-stu-id="a77a2-114">Operations and Functions</span></span> ###

<span data-ttu-id="a77a2-115">Uma das primeiras coisas que um nome deve estabelecer é se um dado símbolo representa uma função ou uma operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="a77a2-116">A diferença entre funções e operações é fundamental para entender como um bloco de código se comporta.</span><span class="sxs-lookup"><span data-stu-id="a77a2-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="a77a2-117">Para comunicar a distinção entre funções e operações aos utilizadores, contamos com os Q# modelos de operações quânticas através da utilização de efeitos secundários.</span><span class="sxs-lookup"><span data-stu-id="a77a2-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="a77a2-118">Isto é, uma operação *faz alguma* coisa.</span><span class="sxs-lookup"><span data-stu-id="a77a2-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="a77a2-119">Em contraste, as funções descrevem as relações matemáticas entre dados.</span><span class="sxs-lookup"><span data-stu-id="a77a2-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="a77a2-120">A expressão `Sin(PI() / 2.0)` *é* `1.0` , e não implica nada sobre o estado de um programa ou seus qubits.</span><span class="sxs-lookup"><span data-stu-id="a77a2-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="a77a2-121">Resumindo, as operações fazem as coisas enquanto as funções são coisas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="a77a2-122">Esta distinção sugere que nomeamos as operações como verbos e funções como substantivos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="a77a2-123">Quando um tipo definido pelo utilizador é declarado, uma nova função que constrói instâncias desse tipo é implicitamente definida ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="a77a2-124">Nessa perspetiva, os tipos definidos pelo utilizador devem ser nomeados como substantivos para que tanto o tipo em si como a função de construtor tenham nomes consistentes.</span><span class="sxs-lookup"><span data-stu-id="a77a2-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="a77a2-125">Quando razoável, certifique-se de que os nomes de operação começam com verbos que indicam claramente o efeito da operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="a77a2-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a77a2-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="a77a2-127">Um caso que merece uma menção especial é quando uma operação toma outra operação como entrada e chama-a.</span><span class="sxs-lookup"><span data-stu-id="a77a2-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="a77a2-128">Nestes casos, as medidas tomadas pela operação de entrada não são claras quando a operação exterior é definida, de modo a que o verbo certo não seja imediatamente claro.</span><span class="sxs-lookup"><span data-stu-id="a77a2-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="a77a2-129">Recomendamos o `Apply` verbo, como em `ApplyIf` , e `ApplyToEach` `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="a77a2-130">Outros verbos podem ser úteis também neste caso, como em `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="a77a2-131">Verbo</span><span class="sxs-lookup"><span data-stu-id="a77a2-131">Verb</span></span> | <span data-ttu-id="a77a2-132">Efeito Esperado</span><span class="sxs-lookup"><span data-stu-id="a77a2-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="a77a2-133">Aplicar</span><span class="sxs-lookup"><span data-stu-id="a77a2-133">Apply</span></span> | <span data-ttu-id="a77a2-134">Uma operação fornecida como entrada é chamada</span><span class="sxs-lookup"><span data-stu-id="a77a2-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="a77a2-135">Declarar</span><span class="sxs-lookup"><span data-stu-id="a77a2-135">Assert</span></span> | <span data-ttu-id="a77a2-136">Uma hipótese sobre o resultado de uma possível medição quântica é verificada por um simulador</span><span class="sxs-lookup"><span data-stu-id="a77a2-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="a77a2-137">Obter estimativa</span><span class="sxs-lookup"><span data-stu-id="a77a2-137">Estimate</span></span> | <span data-ttu-id="a77a2-138">Um valor clássico é devolvido, representando uma estimativa extraída de uma ou mais medições</span><span class="sxs-lookup"><span data-stu-id="a77a2-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="a77a2-139">Medir</span><span class="sxs-lookup"><span data-stu-id="a77a2-139">Measure</span></span> | <span data-ttu-id="a77a2-140">Uma medição quântica é realizada, e o seu resultado é devolvido ao utilizador</span><span class="sxs-lookup"><span data-stu-id="a77a2-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="a77a2-141">Preparação</span><span class="sxs-lookup"><span data-stu-id="a77a2-141">Prepare</span></span> | <span data-ttu-id="a77a2-142">Um dado registo de qubits é inicializado num determinado estado</span><span class="sxs-lookup"><span data-stu-id="a77a2-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="a77a2-143">Sample</span><span class="sxs-lookup"><span data-stu-id="a77a2-143">Sample</span></span> | <span data-ttu-id="a77a2-144">Um valor clássico é devolvido aleatoriamente de alguma distribuição</span><span class="sxs-lookup"><span data-stu-id="a77a2-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="a77a2-145">Para funções, sugerimos evitar a utilização de verbos a favor de substantivos comuns (ver orientação sobre substantivos adequados abaixo) ou adjetivos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="a77a2-146">Em particular, em quase todos os casos, sugerimos usar os particípios passados, quando apropriado, para indicar que um nome de função está fortemente ligado a uma ação ou efeito colateral em outros lugares de um programa quântico.</span><span class="sxs-lookup"><span data-stu-id="a77a2-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="a77a2-147">Por exemplo,  `ControlledOnInt` usa a forma part participle do verbo "control" para indicar que a função age como um adjetivo para modificar o seu argumento.</span><span class="sxs-lookup"><span data-stu-id="a77a2-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="a77a2-148">Este nome tem o benefício adicional de combinar a semântica do `Controlled` functor incorporado, como discutido mais abaixo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="a77a2-149">Da mesma forma, _os substantivos de agente_ podem ser usados para construir funções e nomes de UDT a partir de nomes de operação, como no caso do nome para uma `Encoder` UDT que está fortemente associada a `Encode` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-150">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-151">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-151">We suggest:</span></span>

- <span data-ttu-id="a77a2-152">Utilize verbos para nomes de operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="a77a2-153">Utilize substantivos ou adjetivos para nomes de funções.</span><span class="sxs-lookup"><span data-stu-id="a77a2-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="a77a2-154">Utilize substantivos para tipos e atributos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="a77a2-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="a77a2-155">Para todos os nomes chamados, use `CamelCase` em forte preferência a , ou `pascalCase` `snake_case` `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="a77a2-156">Em particular, certifique-se de que os nomes de chamadas começam com letras maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="a77a2-157">Para todas as variáveis locais, utilize `pascalCase` em forte `CamelCase` `snake_case` preferência, ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="a77a2-158">Em particular, certifique-se de que as variáveis locais começam com letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="a77a2-159">Evite a utilização de sublinhados `_` em nomes de função e operação; onde são necessários níveis adicionais de hierarquia, utilize espaços de nome e pseudónimos de espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="a77a2-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-160">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-160">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="a77a2-161">Nome</span><span class="sxs-lookup"><span data-stu-id="a77a2-161">Name</span></span> | <span data-ttu-id="a77a2-162">Descrição</span><span class="sxs-lookup"><span data-stu-id="a77a2-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="a77a2-163">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="a77a2-164">Utilização clara de um verbo ("refletir") para indicar o efeito da operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="a77a2-165">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="a77a2-166">A utilização da frase substantivo sugere função, em vez de funcionar.</span><span class="sxs-lookup"><span data-stu-id="a77a2-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="a77a2-167">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="a77a2-168">Uso de `snake_case` Q# notação contravenes.</span><span class="sxs-lookup"><span data-stu-id="a77a2-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="a77a2-169">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="a77a2-170">A utilização de sublinhas internas para operar nome contravenções Q# notação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="a77a2-171">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="a77a2-172">A utilização da frase substantivo sugere que a função devolve uma operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="a77a2-173">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="a77a2-174">Uso claro do substantivo ("facto") para indicar que esta é uma função, enquanto o adjetivo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="a77a2-175">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="a77a2-176">A utilização de verbo ("get") sugere que se trata de uma operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="a77a2-177">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="a77a2-178">O uso da frase substantivo refere-se claramente ao resultado de chamar o construtor UDT.</span><span class="sxs-lookup"><span data-stu-id="a77a2-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="a77a2-179">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="a77a2-180">A utilização da frase verbo sugere que o construtor UDT é uma operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="a77a2-181">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="a77a2-182">A utilização da frase substantivo comunica o uso do atributo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="entry-points"></a><span data-ttu-id="a77a2-183">Pontos de Entrada</span><span class="sxs-lookup"><span data-stu-id="a77a2-183">Entry Points</span></span>

<span data-ttu-id="a77a2-184">Ao definir um ponto de entrada num Q# programa, o Q# compilador reconhece o [ `@EntryPoint()` atributo](xref:microsoft.quantum.core.entrypoint) exigindo que os pontos de entrada tenham um nome específico (por exemplo: `main` , ou `Main` `__main__` ).</span><span class="sxs-lookup"><span data-stu-id="a77a2-184">When defining an entry point into a Q# program, the Q# compiler recognizes the [`@EntryPoint()` attribute](xref:microsoft.quantum.core.entrypoint) rather requiring that entry points have a particular name (e.g.: `main`, `Main`, or `__main__`).</span></span>
<span data-ttu-id="a77a2-185">Ou seja, do ponto de vista de um desenvolvedor, os pontos de Q# entrada são operações ordinárias anotadas com `@EntryPoint()` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-185">That is, from the perspective of a Q# developer, entry points are ordinary operations annotated with `@EntryPoint()`.</span></span>
<span data-ttu-id="a77a2-186">Além disso, Q# os pontos de entrada podem ser pontos de entrada para toda uma aplicação (por exemplo, em Q# programas executáveis autónomos), ou podem ser uma interface entre um Q# programa e o programa anfitrião para uma aplicação (ou seja, quando se utiliza Q# com Python ou .NET), de modo que o nome "principal" pode ser enganador quando aplicado a um Q# ponto de entrada.</span><span class="sxs-lookup"><span data-stu-id="a77a2-186">Moreover, Q# entry points may be entry points for an entire application (for example, in Q# standalone executable programs), or may be an interface between a Q# program and the host program for an application (i.e.: when using Q# with Python or .NET), such that the name "main" could be misleading when applied to a Q# entry point.</span></span>

<span data-ttu-id="a77a2-187">Sugerimos a utilização de pontos de nomeação para refletir a utilização do `@EntryPoint()` atributo utilizando os conselhos gerais para as operações de nomeação acima enumeradas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-187">We suggest using naming entry points to reflect the use of the `@EntryPoint()` attribute by using the general advice for naming operations listed above.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="a77a2-188">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-188">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-189">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-189">We suggest:</span></span>

- <span data-ttu-id="a77a2-190">Não nomeie as operações de ponto de entrada como "principais".</span><span class="sxs-lookup"><span data-stu-id="a77a2-190">Do not name entry point operations as "main."</span></span>
- <span data-ttu-id="a77a2-191">Nomeie as operações de ponto de entrada como operações normais.</span><span class="sxs-lookup"><span data-stu-id="a77a2-191">Name entry point operations as ordinary operations.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-192">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-192">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="a77a2-193">Nome</span><span class="sxs-lookup"><span data-stu-id="a77a2-193">Name</span></span> | <span data-ttu-id="a77a2-194">Descrição</span><span class="sxs-lookup"><span data-stu-id="a77a2-194">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="a77a2-195">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-195">☑</span></span> | `@EntryPoint() operation RunSimulation` | <span data-ttu-id="a77a2-196">Comunica claramente o propósito do ponto de entrada através do nome de operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-196">Clearly communicates purpose of entry point through operation name.</span></span> |
| <span data-ttu-id="a77a2-197">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-197">☒</span></span> | <s>`@EntryPoint() operation Main`</s> | <span data-ttu-id="a77a2-198">O uso não `Main` comunica claramente o propósito do ponto de entrada, e é redundante com `@EntryPoint()` atributo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-198">Use of `Main` doesn't clearly communicate purpose of entry point, and is redundant with `@EntryPoint()` attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="a77a2-199">Abreviaturas e Abreviaturas</span><span class="sxs-lookup"><span data-stu-id="a77a2-199">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="a77a2-200">Apesar dos conselhos acima, existem muitas formas de abreviatura que vêem o uso comum e pervasivo na computação quântica.</span><span class="sxs-lookup"><span data-stu-id="a77a2-200">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="a77a2-201">Sugerimos a utilização de abreviaturas existentes e comuns onde ela existe, especialmente para operações intrínsecas ao funcionamento de uma máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-201">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="a77a2-202">Por exemplo, escolhemos o nome `X` em vez de , e em vez de `ApplyX` `Rz` `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-202">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="a77a2-203">Ao utilizar esta abreviatura, os nomes de funcionamento devem ser todos maiúsculas (por exemplo: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="a77a2-203">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="a77a2-204">É necessário ter algum cuidado na aplicação desta convenção no caso de siglas e inicialismos comumente usados, tais como "QFT" para "transformação quântica de Fourier".</span><span class="sxs-lookup"><span data-stu-id="a77a2-204">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="a77a2-205">Sugerimos que se seguem as convenções gerais .NET para a utilização de siglas e inicialismos em nomes completos, que prevêem que:</span><span class="sxs-lookup"><span data-stu-id="a77a2-205">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="a77a2-206">siglas e inicialismos de duas letras são nomeados em maiúscula (por exemplo: `BE` para "big-endian"),</span><span class="sxs-lookup"><span data-stu-id="a77a2-206">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="a77a2-207">todas as siglas e inicialismos mais longos são nomeados `CamelCase` em (por exemplo: `Qft` para "quantum Fourier transform")</span><span class="sxs-lookup"><span data-stu-id="a77a2-207">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="a77a2-208">Assim, uma operação de implementação do QFT poderia ser chamada `QFT` de abreviatura, ou escrita como `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-208">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="a77a2-209">Para operações e funções particularmente utilizadas, pode ser desejável fornecer um nome abreviado como pseudónimo para _uma_ forma mais longa:</span><span class="sxs-lookup"><span data-stu-id="a77a2-209">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="a77a2-210">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-210">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-211">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-211">We suggest:</span></span>

- <span data-ttu-id="a77a2-212">Considere nomes de abreviação geralmente aceites e amplamente utilizados quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="a77a2-212">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="a77a2-213">Utilize maiúsculas para abreviaturas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-213">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="a77a2-214">Utilize maiúsculas para siglas e inicialismos curtos (duas letras).</span><span class="sxs-lookup"><span data-stu-id="a77a2-214">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="a77a2-215">Utilize `CamelCase` para siglas e inicialismos mais longos (três ou mais letras).</span><span class="sxs-lookup"><span data-stu-id="a77a2-215">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-216">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-216">Examples</span></span>](#tab/examples)

| &nbsp;   | <span data-ttu-id="a77a2-217">Nome</span><span class="sxs-lookup"><span data-stu-id="a77a2-217">Name</span></span> | <span data-ttu-id="a77a2-218">Descrição</span><span class="sxs-lookup"><span data-stu-id="a77a2-218">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="a77a2-219">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-219">☑</span></span> | `X` | <span data-ttu-id="a77a2-220">Abreviatura bem entendida para "aplicar uma transformação de $X$"</span><span class="sxs-lookup"><span data-stu-id="a77a2-220">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="a77a2-221">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-221">☑</span></span> | `CNOT` | <span data-ttu-id="a77a2-222">Abreviatura bem entendida para "controlled-NOT"</span><span class="sxs-lookup"><span data-stu-id="a77a2-222">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="a77a2-223">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-223">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="a77a2-224">Abreviatura não deve estar dentro `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-224">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="a77a2-225">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-225">☑</span></span> | `ApplyQft` | <span data-ttu-id="a77a2-226">O inicialismo comum "QFT" aparece como parte de um nome de longa forma.</span><span class="sxs-lookup"><span data-stu-id="a77a2-226">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="a77a2-227">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-227">☑</span></span> | `QFT` | <span data-ttu-id="a77a2-228">O inicialismo comum "QFT" aparece como parte de um nome abreviado.</span><span class="sxs-lookup"><span data-stu-id="a77a2-228">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="a77a2-229">Substantivos adequados em nomes</span><span class="sxs-lookup"><span data-stu-id="a77a2-229">Proper Nouns in Names</span></span> ###

<span data-ttu-id="a77a2-230">Enquanto na física é comum nomear as coisas depois da primeira pessoa a publicar sobre elas, a maioria dos não-físicos não estão familiarizados com os nomes de todos e toda a história.</span><span class="sxs-lookup"><span data-stu-id="a77a2-230">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="a77a2-231">Confiar demasiado na nomeação de convenções da física pode, assim, criar uma barreira substancial à entrada, uma vez que os utilizadores de outras origens devem aprender um grande número de nomes aparentemente opacos para utilizar operações e conceitos comuns.</span><span class="sxs-lookup"><span data-stu-id="a77a2-231">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="a77a2-232">Assim, recomendamos que, sempre que sejam razoáveis, substantivos comuns que descrevam um conceito sejam adotados em forte preferência aos substantivos adequados que descrevem a história da publicação de um conceito.</span><span class="sxs-lookup"><span data-stu-id="a77a2-232">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="a77a2-233">A título particular, as operações SWAP e NÃO duplamente controladas são muitas vezes chamadas de operações "Fredkin" e "Toffoli" na literatura académica, mas são identificadas Q# principalmente como `CSWAP` e `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-233">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="a77a2-234">Em ambos os casos, os comentários da documentação da API fornecem nomes sinónimos baseados em substantivos adequados, juntamente com todas as citações apropriadas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-234">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="a77a2-235">Esta preferência é especialmente importante dado que algum uso de substantivos adequados será sempre necessário - Q# segue a tradição definida por muitas línguas clássicas, por exemplo, e refere-se a `Bool` tipos de referência à lógica booleana, que por sua vez é nomeado em homenagem a George Boole.</span><span class="sxs-lookup"><span data-stu-id="a77a2-235">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="a77a2-236">Alguns conceitos quânticos são igualmente nomeados de forma semelhante, incluindo o `Pauli` tipo incorporado à Q# linguagem.</span><span class="sxs-lookup"><span data-stu-id="a77a2-236">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="a77a2-237">Ao minimizar o uso de substantivos adequados onde tal utilização não é essencial, reduzimos o impacto onde os substantivos adequados não podem ser razoavelmente evitados.</span><span class="sxs-lookup"><span data-stu-id="a77a2-237">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-238">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-238">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="a77a2-239">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-239">We suggest:</span></span>

- <span data-ttu-id="a77a2-240">Evite a utilização de substantivos adequados em nomes.</span><span class="sxs-lookup"><span data-stu-id="a77a2-240">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-241">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-241">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="a77a2-242">Conversões de tipo</span><span class="sxs-lookup"><span data-stu-id="a77a2-242">Type Conversions</span></span> ###

<span data-ttu-id="a77a2-243">Uma vez Q# que é uma linguagem forte e estática, um valor de um tipo só pode ser usado como um valor de outro tipo usando uma chamada explícita para uma função de conversão de tipo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-243">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="a77a2-244">Isto contrasta com as línguas que permitem que os valores mudem os tipos implicitamente (por exemplo: promoção do tipo), ou através do casting.</span><span class="sxs-lookup"><span data-stu-id="a77a2-244">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="a77a2-245">Como resultado, as funções de conversão de tipo desempenham um papel importante no Q# desenvolvimento da biblioteca, e compreendem uma das decisões mais comumente encontradas sobre o nome.</span><span class="sxs-lookup"><span data-stu-id="a77a2-245">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="a77a2-246">Notamos, no entanto, que como as conversões de tipo são sempre _determinísticas,_ podem ser escritas como funções e, portanto, enquadrar-se nos conselhos acima referidos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-246">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="a77a2-247">Em particular, sugerimos que as funções de conversão do tipo nunca devem ser nomeadas como verbos (por exemplo: `ConvertToX` ) ou frases pré-posicionais adverb `ToX` (), mas devem ser nomeadas como frases préposicionais adjetivas que indicam os tipos de origem e destino `XAsY` ().</span><span class="sxs-lookup"><span data-stu-id="a77a2-247">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="a77a2-248">Ao listar tipos de matrizes em nomes de funções de conversão de tipo, recomendamos a abreviatura `Arr` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-248">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="a77a2-249">Salvo circunstâncias excecionais, recomendamos que todas as funções de conversão do tipo sejam nomeadas utilizando `As` para que possam ser rapidamente identificadas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-249">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-250">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-250">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-251">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-251">We suggest:</span></span>

- <span data-ttu-id="a77a2-252">Se uma função converter um valor do tipo `X` para um valor do `Y` tipo, utilize o nome ou `AsY` `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-252">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-253">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-253">Examples</span></span>](#tab/examples)

| &nbsp;   | <span data-ttu-id="a77a2-254">Nome</span><span class="sxs-lookup"><span data-stu-id="a77a2-254">Name</span></span> | <span data-ttu-id="a77a2-255">Descrição</span><span class="sxs-lookup"><span data-stu-id="a77a2-255">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="a77a2-256">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-256">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="a77a2-257">A preposição "a" resulta numa frase verbo, indicando uma operação e não uma função.</span><span class="sxs-lookup"><span data-stu-id="a77a2-257">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="a77a2-258">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-258">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="a77a2-259">O tipo de entrada não é claro a partir do nome da função.</span><span class="sxs-lookup"><span data-stu-id="a77a2-259">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="a77a2-260">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-260">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="a77a2-261">Os tipos de entrada e saída aparecem na ordem errada.</span><span class="sxs-lookup"><span data-stu-id="a77a2-261">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="a77a2-262">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-262">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="a77a2-263">Tanto os tipos de entrada como os tipos de saída são claros.</span><span class="sxs-lookup"><span data-stu-id="a77a2-263">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="a77a2-264">Nomes Privados ou Internos</span><span class="sxs-lookup"><span data-stu-id="a77a2-264">Private or Internal Names</span></span> ###

<span data-ttu-id="a77a2-265">Em muitos casos, um nome destina-se estritamente a ser utilizado internamente numa biblioteca ou projeto, e não é uma parte garantida da API oferecida por uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a77a2-265">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="a77a2-266">É útil indicar claramente que é esse o caso quando se nomeia funções e operações, de modo a que as dependências acidentais do código interno sejam tornadas óbvias.</span><span class="sxs-lookup"><span data-stu-id="a77a2-266">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="a77a2-267">Se uma operação ou função não for destinada a uso direto, mas sim a utilização de uma chamada correspondente que aja por aplicação parcial, considere utilizar um nome que comece pela `internal` palavra-chave para a chamada que é parcialmente aplicada.</span><span class="sxs-lookup"><span data-stu-id="a77a2-267">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with the `internal` keyword for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-268">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-268">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-269">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-269">We suggest:</span></span>

- <span data-ttu-id="a77a2-270">Quando uma função, operação ou tipo definido pelo utilizador não faz parte da API pública para uma Q# biblioteca ou programa, certifique-se de que está marcada como interna colocando a `internal` palavra-chave antes do `function` , ou `operation` `newtype` declaração.</span><span class="sxs-lookup"><span data-stu-id="a77a2-270">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that it is marked as internal by placing the `internal` keyword before the `function`, `operation`, or `newtype` declaration.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-271">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-271">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="a77a2-272">Nome</span><span class="sxs-lookup"><span data-stu-id="a77a2-272">Name</span></span> | <span data-ttu-id="a77a2-273">Descrição</span><span class="sxs-lookup"><span data-stu-id="a77a2-273">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="a77a2-274">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-274">☒</span></span> | <s>`operation _ApplyDecomposedOperation`</s> | <span data-ttu-id="a77a2-275">Não utilize um sublinhado `_` que indique que esta operação é apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="a77a2-275">Do not use an underscore `_` to indicate that this operation is for internal use only.</span></span> |
| <span data-ttu-id="a77a2-276">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-276">☑</span></span> | `internal operation ApplyDecomposedOperation` | <span data-ttu-id="a77a2-277">A `internal` palavra-chave no início indica claramente que esta operação é apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="a77a2-277">The `internal` keyword at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***
### <a name="variants"></a><span data-ttu-id="a77a2-278">Variantes</span><span class="sxs-lookup"><span data-stu-id="a77a2-278">Variants</span></span> ###

<span data-ttu-id="a77a2-279">Embora esta limitação possa não persistir em futuras versões de Q# , é atualmente o caso de existirem frequentemente grupos de operações ou funções relacionadas que se distinguem pelo qual os funtores suportam os seus inputs, ou pelos tipos concretos dos seus argumentos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-279">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="a77a2-280">Estes grupos podem ser distinguidos usando o mesmo nome de raiz, seguidos por uma ou duas letras que indicam a sua variante.</span><span class="sxs-lookup"><span data-stu-id="a77a2-280">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="a77a2-281">Sufixo</span><span class="sxs-lookup"><span data-stu-id="a77a2-281">Suffix</span></span> | <span data-ttu-id="a77a2-282">Significado</span><span class="sxs-lookup"><span data-stu-id="a77a2-282">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="a77a2-283">Entrada esperada para apoiar `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="a77a2-283">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="a77a2-284">Entrada esperada para apoiar `Controlled`</span><span class="sxs-lookup"><span data-stu-id="a77a2-284">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="a77a2-285">Entrada esperada para apoiar `Controlled` e `Adjoint`</span><span class="sxs-lookup"><span data-stu-id="a77a2-285">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="a77a2-286">Entradas ou entradas são do tipo `Int`</span><span class="sxs-lookup"><span data-stu-id="a77a2-286">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="a77a2-287">Entradas ou entradas são do tipo `Double`</span><span class="sxs-lookup"><span data-stu-id="a77a2-287">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="a77a2-288">Entradas ou entradas são do tipo `BigInt`</span><span class="sxs-lookup"><span data-stu-id="a77a2-288">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="a77a2-289">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-289">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-290">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-290">We suggest:</span></span>

- <span data-ttu-id="a77a2-291">Se uma função ou funcionamento não estiver relacionado com funções ou operações semelhantes pelos tipos e suporte functor das suas entradas, não utilize um sufixo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-291">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="a77a2-292">Se uma função ou funcionamento estiver relacionado com quaisquer funções ou operações semelhantes pelos tipos e suporte functor das suas entradas, utilize sufixos como no quadro acima para distinguir variantes.</span><span class="sxs-lookup"><span data-stu-id="a77a2-292">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-293">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-293">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="a77a2-294">Argumentos e Variáveis</span><span class="sxs-lookup"><span data-stu-id="a77a2-294">Arguments and Variables</span></span> ###

<span data-ttu-id="a77a2-295">Um objectivo-chave do Q# código para uma função ou operação é que seja facilmente lido e compreendido.</span><span class="sxs-lookup"><span data-stu-id="a77a2-295">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="a77a2-296">Da mesma forma, os nomes das entradas e dos argumentos de tipo devem comunicar como uma função ou argumento será usado uma vez fornecido.</span><span class="sxs-lookup"><span data-stu-id="a77a2-296">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="a77a2-297">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-298">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-298">We suggest:</span></span>

- <span data-ttu-id="a77a2-299">Para todos os nomes variáveis e de entrada, utilize `pascalCase` em forte `CamelCase` `snake_case` preferência, ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-299">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="a77a2-300">Os nomes de entrada devem ser descritivos; evitar um ou dois nomes de letras sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="a77a2-300">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="a77a2-301">As operações e funções que aceitam exatamente um argumento de tipo devem denotar esse argumento de tipo `T` quando o seu papel é óbvio.</span><span class="sxs-lookup"><span data-stu-id="a77a2-301">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="a77a2-302">Se uma função ou operação tiver múltiplos argumentos de tipo, ou se o papel de um único argumento de tipo não for óbvio, considere a utilização de uma palavra maiúscula curta prefaciada por `T` (por exemplo: `TOutput` ) para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-302">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="a77a2-303">Não inclua nomes de tipo em argumentos e nomes variáveis; esta informação pode e deve ser fornecida pelo seu ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="a77a2-303">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="a77a2-304">Denotar tipos de escalar pelos seus nomes `flagQubit` literais () e tipos de matrizes por um plural ( `measResults` ).</span><span class="sxs-lookup"><span data-stu-id="a77a2-304">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="a77a2-305">Para matrizes de qubits em particular, considere denotar tais tipos por `Register` onde o nome se refere a uma sequência de qubits que estão intimamente relacionados de alguma forma.</span><span class="sxs-lookup"><span data-stu-id="a77a2-305">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="a77a2-306">As variáveis utilizadas como índices em matrizes devem começar `idx` e devem ser singulares (por exemplo: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="a77a2-306">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="a77a2-307">Em especial, evitem utilizar nomes variáveis de letra única como índices; considerar a `idx` utilização no mínimo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-307">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="a77a2-308">As variáveis utilizadas para manter os comprimentos das matrizes devem começar `n` e devem ser pluralizadas (por exemplo: `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="a77a2-308">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-309">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-309">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="a77a2-310">Itens nomeados para o tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="a77a2-310">User-Defined Type Named Items</span></span> ###

<span data-ttu-id="a77a2-311">Os itens nomeados em tipos definidos pelo utilizador devem ser nomeados como `CamelCase` , mesmo na entrada para os construtores UDT.</span><span class="sxs-lookup"><span data-stu-id="a77a2-311">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="a77a2-312">Isto ajuda a separar claramente os itens nomeados de referências a variáveis de âmbito local quando se utilizam notações acessórias (por exemplo: `callable::Apply` ) ou notação de cópia e atualização ( `set arr w/= Data <- newData` ).</span><span class="sxs-lookup"><span data-stu-id="a77a2-312">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-313">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-313">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-314">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-314">We suggest:</span></span>

- <span data-ttu-id="a77a2-315">Os itens nomeados nos construtores UDT devem ser nomeados como `CamelCase` ; ou seja, devem começar com uma maiúscula inicial.</span><span class="sxs-lookup"><span data-stu-id="a77a2-315">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="a77a2-316">Os itens nomeados que se resolvem para as operações devem ser nomeados como fases de verbo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-316">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="a77a2-317">Os itens nomeados que não se resolvem para operações devem ser nomeados como frases substantivos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-317">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="a77a2-318">Para as UDTs que envolvem operações, deve ser definido um único item chamado. `Apply`</span><span class="sxs-lookup"><span data-stu-id="a77a2-318">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-319">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-319">Examples</span></span>](#tab/examples)

| &nbsp;  | <span data-ttu-id="a77a2-320">Fragmento de código</span><span class="sxs-lookup"><span data-stu-id="a77a2-320">Snippet</span></span> | <span data-ttu-id="a77a2-321">Descrição</span><span class="sxs-lookup"><span data-stu-id="a77a2-321">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="a77a2-322">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-322">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="a77a2-323">O nome `Apply` é uma `CamelCase` frase verbo formatada, sugerindo que o item nomeado é uma operação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-323">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="a77a2-324">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-324">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="a77a2-325">Os itens nomeados devem começar com uma letra maiúscula inicial.</span><span class="sxs-lookup"><span data-stu-id="a77a2-325">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="a77a2-326">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-326">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="a77a2-327">Os itens nomeados que se resolvem para funções devem ser nomeados como frases substantivos, e não como frases verbos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-327">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="a77a2-328">Convenções de Entrada</span><span class="sxs-lookup"><span data-stu-id="a77a2-328">Input Conventions</span></span> ##

<span data-ttu-id="a77a2-329">Quando um desenvolvedor chama para uma operação ou função, as várias entradas para essa operação ou função devem ser especificadas numa determinada ordem, aumentando a carga cognitiva que um desenvolvedor enfrenta para fazer uso de uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a77a2-329">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="a77a2-330">Em particular, a tarefa de lembrar as encomendas de entrada é muitas vezes uma distração da tarefa em questão: programar uma implementação de um algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="a77a2-330">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="a77a2-331">Embora o rico suporte IDE possa mitigar isso em grande medida, o bom design e a adesão a convenções comuns também podem ajudar a minimizar a carga cognitiva imposta por uma API.</span><span class="sxs-lookup"><span data-stu-id="a77a2-331">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="a77a2-332">Sempre que possível, pode ser útil reduzir o número de entradas esperadas por uma operação ou função, de modo que o papel de cada entrada seja mais imediatamente óbvio tanto para os desenvolvedores que ligam para essa operação ou função, como para os desenvolvedores lerem esse código mais tarde.</span><span class="sxs-lookup"><span data-stu-id="a77a2-332">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="a77a2-333">Especialmente quando não é possível ou razoável reduzir o número de argumentos para uma operação ou função, é importante ter uma ordem consistente que minimize a surpresa que um utilizador enfrenta ao prever a ordem de entradas.</span><span class="sxs-lookup"><span data-stu-id="a77a2-333">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="a77a2-334">Recomendamos uma convenção de pedido de entrada que deriva em grande parte do pensamento da aplicação parcial como uma generalização do currying f(x, y) ≡ f(x)(y).</span><span class="sxs-lookup"><span data-stu-id="a77a2-334">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="a77a2-335">Assim, a aplicação parcial dos primeiros argumentos deverá resultar numa chamada que seja útil por si só sempre que isso seja razoável.</span><span class="sxs-lookup"><span data-stu-id="a77a2-335">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="a77a2-336">Seguindo este princípio, considere a utilização da seguinte ordem de argumentos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-336">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="a77a2-337">Argumentos clássicos não-chamados, tais como ângulos, vetores de poderes, etc.</span><span class="sxs-lookup"><span data-stu-id="a77a2-337">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="a77a2-338">Argumentos insutilizáveis (funções e argumentos).</span><span class="sxs-lookup"><span data-stu-id="a77a2-338">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="a77a2-339">Se ambas as funções e operações forem tomadas como argumentos, considere a colocação de operações após funções.</span><span class="sxs-lookup"><span data-stu-id="a77a2-339">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="a77a2-340">As coleções atuavam com argumentos inutilizáveis de forma semelhante `Map` `Iter` a, `Enumerate` e `Fold` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-340">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="a77a2-341">Argumentos qubit usados como controlos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-341">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="a77a2-342">Argumentos qubit usados como alvos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-342">Qubit arguments used as targets.</span></span>

<span data-ttu-id="a77a2-343">Considere uma operação `ApplyPhaseEstimationIteration` para utilização na estimativa de fase que toma um ângulo e um oráculo, passa o ângulo para `Rz` modificado por uma série de diferentes fatores de escala, e depois controla as aplicações do oráculo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-343">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="a77a2-344">Ordenaríamos que os inputs fossem `ApplyPhaseEstimationIteration` da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a77a2-344">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="a77a2-345">Como caso especial de minimização da surpresa, algumas funções e operações imitam o comportamento dos functores embutidos `Adjoint` e `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="a77a2-345">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="a77a2-346">Por exemplo, `ControlledOnInt<'T>` tem tipo , tal que age como o `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` `ControlledOnInt<Qubit[]>(5, _)` `Controlled` functor, mas na condição de o registo de controlo representar o estado $\ket {5} = \ket {101} $.</span><span class="sxs-lookup"><span data-stu-id="a77a2-346">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="a77a2-347">Assim, um desenvolvedor espera que as entradas para `ControlledOnInt` colocar o ser calável em último lugar, e que a operação resultante toma como sua entrada `(Qubit[], 'T)` --- a mesma ordem seguida pela saída do `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="a77a2-347">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-348">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-348">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-349">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-349">We suggest:</span></span>

- <span data-ttu-id="a77a2-350">Utilize pedidos de entrada consistentes com a utilização de aplicações parciais.</span><span class="sxs-lookup"><span data-stu-id="a77a2-350">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="a77a2-351">Utilize pedidos de entrada consistentes com functors incorporados.</span><span class="sxs-lookup"><span data-stu-id="a77a2-351">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="a77a2-352">Coloque todas as entradas clássicas antes de qualquer entrada quântica.</span><span class="sxs-lookup"><span data-stu-id="a77a2-352">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-353">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-353">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="a77a2-354">Convenções de Documentação</span><span class="sxs-lookup"><span data-stu-id="a77a2-354">Documentation Conventions</span></span> ##

<span data-ttu-id="a77a2-355">O Q# idioma permite anexar documentação a operações, funções e tipos definidos pelo utilizador através da utilização de comentários de documentação especialmente formatados.</span><span class="sxs-lookup"><span data-stu-id="a77a2-355">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="a77a2-356">Denotados por triplo-slashes ( `///` ), estes comentários documentais são pequenos documentos [markdown com sabor DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) que podem ser usados para descrever o propósito de cada operação, função e tipo definido pelo utilizador, o que cada um espera, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a77a2-356">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="a77a2-357">O compilador fornecido com o Kit de Desenvolvimento Quântico extrai estes comentários e usa-os para ajudar a tipet documentação semelhante à da https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="a77a2-357">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="a77a2-358">Da mesma forma, o servidor de idiomas fornecido com o Kit de Desenvolvimento Quântico utiliza estes comentários para fornecer ajuda aos utilizadores quando pairam sobre símbolos no seu Q# código.</span><span class="sxs-lookup"><span data-stu-id="a77a2-358">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="a77a2-359">Fazer uso de comentários documentais pode, assim, ajudar os utilizadores a dar sentido ao código, fornecendo uma referência útil para detalhes que não são facilmente expressos usando as outras convenções neste documento.</span><span class="sxs-lookup"><span data-stu-id="a77a2-359">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

> [!div class="nextstepaction"]
> <span data-ttu-id="a77a2-360">[Referência de sintaxe de comentário de documentação](xref:microsoft.quantum.guide.filestructure#documentation-comments).</span><span class="sxs-lookup"><span data-stu-id="a77a2-360">[Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments).</span></span>

<span data-ttu-id="a77a2-361">Para utilizar eficazmente esta funcionalidade para ajudar os utilizadores, recomendamos ter algumas coisas em mente enquanto escreve comentários de documentação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-361">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-362">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-362">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="a77a2-363">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-363">We suggest:</span></span>

- <span data-ttu-id="a77a2-364">Cada função pública, operação e tipo definido pelo utilizador devem ser imediatamente precedidos por um comentário de documentação.</span><span class="sxs-lookup"><span data-stu-id="a77a2-364">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="a77a2-365">No mínimo, cada comentário de documentação deve incluir as seguintes secções:</span><span class="sxs-lookup"><span data-stu-id="a77a2-365">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="a77a2-366">Resumo</span><span class="sxs-lookup"><span data-stu-id="a77a2-366">Summary</span></span>
    - <span data-ttu-id="a77a2-367">Entrada</span><span class="sxs-lookup"><span data-stu-id="a77a2-367">Input</span></span>
    - <span data-ttu-id="a77a2-368">Saída (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="a77a2-368">Output (if applicable)</span></span>
- <span data-ttu-id="a77a2-369">Certifique-se de que todos os resumos são duas frases ou menos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-369">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="a77a2-370">Se for necessário mais espaço, forneça uma `# Description` secção imediatamente a seguir com todos os `# Summary` detalhes.</span><span class="sxs-lookup"><span data-stu-id="a77a2-370">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="a77a2-371">Quando razoável, não inclua matemática em resumos, uma vez que nem todos os clientes suportam a notação TeX em resumos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-371">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="a77a2-372">Note que ao escrever documentos em prosa (por exemplo, TeX ou Markdown), pode ser preferível utilizar comprimentos de linha mais longos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-372">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="a77a2-373">Fornecer todas as expressões matemáticas relevantes na `# Description` secção.</span><span class="sxs-lookup"><span data-stu-id="a77a2-373">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="a77a2-374">Ao descrever as entradas, não repita os tipos de cada entrada, uma vez que estes podem ser deduzidos pelo compilador e corre o risco de introduzir inconsistência.</span><span class="sxs-lookup"><span data-stu-id="a77a2-374">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="a77a2-375">Fornecer exemplos conforme apropriado, cada um na sua própria `# Example` secção.</span><span class="sxs-lookup"><span data-stu-id="a77a2-375">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="a77a2-376">Descreva brevemente cada exemplo antes de listar o código.</span><span class="sxs-lookup"><span data-stu-id="a77a2-376">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="a77a2-377">Cite todas as publicações académicas relevantes (por exemplo: papéis, procedimentos, posts de blog e implementações alternativas) numa `# References` secção como uma lista de links.</span><span class="sxs-lookup"><span data-stu-id="a77a2-377">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="a77a2-378">Certifique-se de que, sempre que possível, todas as ligações de citação são para identificadores permanentes e imutáveis (DOIs ou números arXiv em versão).</span><span class="sxs-lookup"><span data-stu-id="a77a2-378">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="a77a2-379">Quando uma operação ou função estiver relacionada com outras operações ou funções por variantes do functor, liste outras variantes como balas na `# See Also` secção.</span><span class="sxs-lookup"><span data-stu-id="a77a2-379">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="a77a2-380">Deixe uma linha de comentário em branco entre as secções de nível 1 ( `/// #` ), mas não deixe uma linha em branco entre as secções de nível 2 ( `/// ##` ).</span><span class="sxs-lookup"><span data-stu-id="a77a2-380">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-381">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-381">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="a77a2-382">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-382">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="a77a2-383">Convenções de Formatação</span><span class="sxs-lookup"><span data-stu-id="a77a2-383">Formatting Conventions</span></span> ##

<span data-ttu-id="a77a2-384">Além das sugestões anteriores, é útil ajudar a tornar o código o mais legível possível para usar regras de formatação consistentes.</span><span class="sxs-lookup"><span data-stu-id="a77a2-384">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="a77a2-385">Tais regras de formatação por natureza tendem a ser um pouco arbitrárias e fortemente à altura da estética pessoal.</span><span class="sxs-lookup"><span data-stu-id="a77a2-385">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="a77a2-386">No entanto, recomendamos a manutenção de um conjunto consistente de convenções de formatação dentro de um grupo de colaboradores, e especialmente para grandes Q# projetos como o próprio Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="a77a2-386">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="a77a2-387">Estas regras podem ser aplicadas automaticamente utilizando a ferramenta de formatação integrada com o Q# compilador.</span><span class="sxs-lookup"><span data-stu-id="a77a2-387">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="a77a2-388">Orientação</span><span class="sxs-lookup"><span data-stu-id="a77a2-388">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="a77a2-389">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="a77a2-389">We suggest:</span></span>

- <span data-ttu-id="a77a2-390">Utilize quatro espaços em vez de separadores para portabilidade.</span><span class="sxs-lookup"><span data-stu-id="a77a2-390">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="a77a2-391">Por exemplo, no Código VS:</span><span class="sxs-lookup"><span data-stu-id="a77a2-391">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="a77a2-392">Embrulho de linha em 79 caracteres onde razoável.</span><span class="sxs-lookup"><span data-stu-id="a77a2-392">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="a77a2-393">Use espaços em torno de operadores binários.</span><span class="sxs-lookup"><span data-stu-id="a77a2-393">Use spaces around binary operators.</span></span>
- <span data-ttu-id="a77a2-394">Utilize espaços em ambos os lados dos cólons utilizados para anotações de tipo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-394">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="a77a2-395">Utilize um único espaço após vírgulas utilizadas em matrizes e tuple literais (por exemplo: nas entradas para funções e operações).</span><span class="sxs-lookup"><span data-stu-id="a77a2-395">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="a77a2-396">Não utilize espaços após função, funcionamento ou nomes UDT, ou após as `@` declarações de atributos.</span><span class="sxs-lookup"><span data-stu-id="a77a2-396">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="a77a2-397">Cada declaração de atributos deve estar na sua própria linha.</span><span class="sxs-lookup"><span data-stu-id="a77a2-397">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="a77a2-398">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a77a2-398">Examples</span></span>](#tab/examples)

| &nbsp; | <span data-ttu-id="a77a2-399">Fragmento de código</span><span class="sxs-lookup"><span data-stu-id="a77a2-399">Snippet</span></span> | <span data-ttu-id="a77a2-400">Descrição</span><span class="sxs-lookup"><span data-stu-id="a77a2-400">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="a77a2-401">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-401">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="a77a2-402">Use espaços em torno de operadores binários.</span><span class="sxs-lookup"><span data-stu-id="a77a2-402">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="a77a2-403">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-403">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="a77a2-404">Use espaços em torno de cólons de anotação tipo.</span><span class="sxs-lookup"><span data-stu-id="a77a2-404">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="a77a2-405">☑</span><span class="sxs-lookup"><span data-stu-id="a77a2-405">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="a77a2-406">Os itens na entrada são corretamente espaçados para a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="a77a2-406">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="a77a2-407">☒</span><span class="sxs-lookup"><span data-stu-id="a77a2-407">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="a77a2-408">Os espaços devem ser suprimidos após a função, o funcionamento ou os nomes de UDT.</span><span class="sxs-lookup"><span data-stu-id="a77a2-408">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***
