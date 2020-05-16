---
title: Guia de estilo Microsoft Q#
description: Conheça as convenções de nomeação, entrada, documentação e formatação para programas e bibliotecas Q# .
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: dfb2b1779e3ddc77fc74697bc4dc2904b1a0c70f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426933"
---
# <a name="q-style-guide"></a><span data-ttu-id="9de6a-103">Guia de estilo Q#</span><span class="sxs-lookup"><span data-stu-id="9de6a-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="9de6a-104">Convenções Gerais</span><span class="sxs-lookup"><span data-stu-id="9de6a-104">General Conventions</span></span> ##

<span data-ttu-id="9de6a-105">As convenções sugeridas neste guia destinam-se a ajudar a tornar os programas e bibliotecas escritos em Q# mais fáceis de ler e entender.</span><span class="sxs-lookup"><span data-stu-id="9de6a-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="9de6a-106">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-106">Guidance</span></span>

<span data-ttu-id="9de6a-107">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-107">We suggest:</span></span>

- <span data-ttu-id="9de6a-108">Nunca ignore uma convenção a menos que o faça intencionalmente para fornecer um código mais legível e compreensível para os seus utilizadores.</span><span class="sxs-lookup"><span data-stu-id="9de6a-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="9de6a-109">Convenções de Nomeação</span><span class="sxs-lookup"><span data-stu-id="9de6a-109">Naming Conventions</span></span> ##

<span data-ttu-id="9de6a-110">Ao oferecer o Kit de Desenvolvimento Quântico, esforçamo-nos por nomes de função e operação que ajudam os desenvolvedores quânticos a escrever programas que são fáceis de ler e que minimizam a surpresa.</span><span class="sxs-lookup"><span data-stu-id="9de6a-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="9de6a-111">Uma parte importante disso é que, quando escolhemos nomes para funções, operações e tipos, estamos a estabelecer o *vocabulário* que os programadores usam para expressar conceitos quânticos; com as nossas escolhas, ou ajudamos ou os dificultamos no seu esforço para comunicar claramente.</span><span class="sxs-lookup"><span data-stu-id="9de6a-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="9de6a-112">Isto coloca-nos a responsabilidade de nos assegurarmos de que os nomes que introduzimos ofereçam clareza em vez de obscuridade.</span><span class="sxs-lookup"><span data-stu-id="9de6a-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="9de6a-113">Nesta secção, detalhamos como cumprimos esta obrigação em termos de orientação explícita que nos ajuda a fazer o melhor pela comunidade de desenvolvimento Q#.</span><span class="sxs-lookup"><span data-stu-id="9de6a-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="9de6a-114">Operações e Funções</span><span class="sxs-lookup"><span data-stu-id="9de6a-114">Operations and Functions</span></span> ###

<span data-ttu-id="9de6a-115">Uma das primeiras coisas que um nome deve estabelecer é se um determinado símbolo representa uma função ou uma operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="9de6a-116">A diferença entre funções e operações é fundamental para entender como um bloco de código se comporta.</span><span class="sxs-lookup"><span data-stu-id="9de6a-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="9de6a-117">Para comunicar a distinção entre funções e operações aos utilizadores, contamos com as operações quânticas dos modelos Q# através da utilização de efeitos secundários.</span><span class="sxs-lookup"><span data-stu-id="9de6a-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="9de6a-118">Isto é, uma operação *faz* alguma coisa.</span><span class="sxs-lookup"><span data-stu-id="9de6a-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="9de6a-119">Em contraste, as funções descrevem as relações matemáticas entre os dados.</span><span class="sxs-lookup"><span data-stu-id="9de6a-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="9de6a-120">A expressão `Sin(PI() / 2.0)` *é* `1.0` , e não implica nada sobre o estado de um programa ou os seus qubits.</span><span class="sxs-lookup"><span data-stu-id="9de6a-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="9de6a-121">Resumindo, as operações fazem as coisas enquanto as funções são coisas.</span><span class="sxs-lookup"><span data-stu-id="9de6a-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="9de6a-122">Esta distinção sugere que nomeamos as operações como verbos e funciona como substantivos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="9de6a-123">Quando um tipo definido pelo utilizador é declarado, uma nova função que constrói instâncias desse tipo é implicitamente definida ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="9de6a-124">Nessa perspetiva, os tipos definidos pelo utilizador devem ser nomeados como substantivos para que tanto o tipo como a função do construtor tenham nomes consistentes.</span><span class="sxs-lookup"><span data-stu-id="9de6a-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="9de6a-125">Se for razoável, certifique-se de que os nomes da operação começam com verbos que indiquem claramente o efeito tomado pela operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="9de6a-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9de6a-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="9de6a-127">Um caso que merece uma menção especial é quando uma operação toma outra operação como entrada e chama-a.</span><span class="sxs-lookup"><span data-stu-id="9de6a-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="9de6a-128">Nesses casos, as medidas tomadas pela operação de entrada não são claras quando a operação externa é definida, de modo a que o verbo direito não seja imediatamente claro.</span><span class="sxs-lookup"><span data-stu-id="9de6a-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="9de6a-129">Recomendamos o `Apply` verbo, como `ApplyIf` em, `ApplyToEach` e `ApplyToFirst` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="9de6a-130">Outros verbos podem ser úteis também neste caso, assim como em `IterateThroughCartesianPower` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="9de6a-131">Verbo</span><span class="sxs-lookup"><span data-stu-id="9de6a-131">Verb</span></span> | <span data-ttu-id="9de6a-132">Efeito Esperado</span><span class="sxs-lookup"><span data-stu-id="9de6a-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="9de6a-133">Aplicar</span><span class="sxs-lookup"><span data-stu-id="9de6a-133">Apply</span></span> | <span data-ttu-id="9de6a-134">Uma operação fornecida como entrada é chamada</span><span class="sxs-lookup"><span data-stu-id="9de6a-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="9de6a-135">Declarar</span><span class="sxs-lookup"><span data-stu-id="9de6a-135">Assert</span></span> | <span data-ttu-id="9de6a-136">Uma hipótese sobre o resultado de uma possível medição quântica é verificada por um simulador</span><span class="sxs-lookup"><span data-stu-id="9de6a-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="9de6a-137">Estimativa</span><span class="sxs-lookup"><span data-stu-id="9de6a-137">Estimate</span></span> | <span data-ttu-id="9de6a-138">Um valor clássico é devolvido, representando uma estimativa extraída de uma ou mais medidas</span><span class="sxs-lookup"><span data-stu-id="9de6a-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="9de6a-139">Medir</span><span class="sxs-lookup"><span data-stu-id="9de6a-139">Measure</span></span> | <span data-ttu-id="9de6a-140">Uma medição quântica é realizada, e o seu resultado é devolvido ao utilizador</span><span class="sxs-lookup"><span data-stu-id="9de6a-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="9de6a-141">Preparação</span><span class="sxs-lookup"><span data-stu-id="9de6a-141">Prepare</span></span> | <span data-ttu-id="9de6a-142">Um determinado registo de qubits é inicializado num determinado estado</span><span class="sxs-lookup"><span data-stu-id="9de6a-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="9de6a-143">Sample</span><span class="sxs-lookup"><span data-stu-id="9de6a-143">Sample</span></span> | <span data-ttu-id="9de6a-144">Um valor clássico é devolvido aleatoriamente de alguma distribuição</span><span class="sxs-lookup"><span data-stu-id="9de6a-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="9de6a-145">Para funções, sugerimos evitar a utilização de verbos a favor de substantivos comuns (ver orientação sobre substantivos adequados abaixo) ou adjetivos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="9de6a-146">Em particular, em quase todos os casos, sugerimos a utilização de particípios passados, sempre que apropriado, para indicar que um nome de função está fortemente ligado a uma ação ou efeito colateral em outros lugares de um programa quântico.</span><span class="sxs-lookup"><span data-stu-id="9de6a-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="9de6a-147">Por exemplo, `ControlledOnInt` utiliza a parte do "controlo" do verbo para indicar que a função funciona como um adjetivo para modificar o seu argumento.</span><span class="sxs-lookup"><span data-stu-id="9de6a-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="9de6a-148">Este nome tem o benefício adicional de combinar a semântica do `Controlled` functor incorporado, como discutido mais abaixo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="9de6a-149">Da mesma forma, _os substantivos_ de agente podem ser usados para construir nomes de funções e UDT a partir de nomes de operação, como no caso do nome `Encoder` para um UDT fortemente associado `Encode` a .</span><span class="sxs-lookup"><span data-stu-id="9de6a-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-150">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-151">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-151">We suggest:</span></span>

- <span data-ttu-id="9de6a-152">Utilize verbos para nomes de operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="9de6a-153">Utilize substantivos ou adjetivos para nomes de funções.</span><span class="sxs-lookup"><span data-stu-id="9de6a-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="9de6a-154">Utilize substantivos para tipos e atributos definidos pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="9de6a-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="9de6a-155">Para todos os nomes que podem ser chamados, utilize `CamelCase` com forte preferência `pascalCase` `snake_case` para, ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="9de6a-156">Em particular, certifique-se de que os nomes insensíveis começam com letras maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="9de6a-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="9de6a-157">Para todas as variáveis locais, use `pascalCase` com forte preferência `CamelCase` `snake_case` para, ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="9de6a-158">Em particular, certifique-se de que as variáveis locais começam com letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9de6a-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="9de6a-159">Evite a utilização de sublinhados em nomes de `_` funções e funcionamento; onde sejam necessários níveis adicionais de hierarquia, utilize espaços de nome e pseudónimos de espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="9de6a-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-160">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="9de6a-161">Name</span><span class="sxs-lookup"><span data-stu-id="9de6a-161">Name</span></span> | <span data-ttu-id="9de6a-162">Descrição</span><span class="sxs-lookup"><span data-stu-id="9de6a-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="9de6a-163">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="9de6a-164">Utilização clara de um verbo ("refletir") para indicar o efeito da operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="9de6a-165">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="9de6a-166">O uso da frase do substantivo sugere função, em vez de funcionar.</span><span class="sxs-lookup"><span data-stu-id="9de6a-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="9de6a-167">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="9de6a-168">Uso de `snake_case` contravenções Notação Q#.</span><span class="sxs-lookup"><span data-stu-id="9de6a-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="9de6a-169">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="9de6a-170">O uso de sublinhados internos para o nome de operação viola a notação Q#.</span><span class="sxs-lookup"><span data-stu-id="9de6a-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="9de6a-171">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="9de6a-172">A utilização da frase do substantivo sugere que a função devolve uma operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="9de6a-173">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="9de6a-174">Uso claro do substantivo ("facto") para indicar que esta é uma função, enquanto o adjetivo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="9de6a-175">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="9de6a-176">A utilização do verbo ("get") sugere que se trata de uma operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="9de6a-177">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="9de6a-178">O uso da frase substantivo refere-se claramente ao resultado de chamar o construtor da UDT.</span><span class="sxs-lookup"><span data-stu-id="9de6a-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="9de6a-179">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="9de6a-180">O uso da frase verbo sugere que o construtor uDT é uma operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="9de6a-181">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="9de6a-182">O uso da frase substantivo comunica o uso do atributo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="9de6a-183">Abreviaturas e Abreviaturas</span><span class="sxs-lookup"><span data-stu-id="9de6a-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="9de6a-184">Apesar dos conselhos acima referidos, existem muitas formas de abreviatura que vêem o uso comum e pervasivo na computação quântica.</span><span class="sxs-lookup"><span data-stu-id="9de6a-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="9de6a-185">Sugerimos a utilização de abreviaturas existentes e comuns onde ela existe, especialmente para operações intrínsecas ao funcionamento de uma máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="9de6a-186">Por exemplo, escolhemos o nome `X` em vez de , e em vez de `ApplyX` `Rz` `RotateAboutZ` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="9de6a-187">Quando utilizar esta abreviatura, os nomes de funcionamento devem ser todos maiúsculos (por exemplo: `MAJ` ).</span><span class="sxs-lookup"><span data-stu-id="9de6a-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="9de6a-188">É necessário algum cuidado ao aplicar esta convenção no caso de siglas e rubricas comumente usadas, como "QFT" para "quantum Fourier transform".</span><span class="sxs-lookup"><span data-stu-id="9de6a-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="9de6a-189">Sugerimos que se seguem convenções gerais .NET para a utilização de siglas e rubricas em nomes completos, que prescrevem que:</span><span class="sxs-lookup"><span data-stu-id="9de6a-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="9de6a-190">as siglas de duas letras e os iniciantes são nomeados em maiúsculas (por exemplo: `BE` para "grande endian"),</span><span class="sxs-lookup"><span data-stu-id="9de6a-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="9de6a-191">todos os siglas e iniciais mais longos são nomeados em `CamelCase` (por exemplo: `Qft` para "quantum Fourier transform")</span><span class="sxs-lookup"><span data-stu-id="9de6a-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="9de6a-192">Assim, uma operação de execução do QFT pode ser chamada `QFT` de abreviatura, ou escrita como `ApplyQft` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="9de6a-193">Para operações e funções particularmente utilizadas, pode ser desejável fornecer um nome abreviado como _pseudónimo_ para uma forma mais longa:</span><span class="sxs-lookup"><span data-stu-id="9de6a-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="9de6a-194">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-195">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-195">We suggest:</span></span>

- <span data-ttu-id="9de6a-196">Considere nomes de abreviaturas geralmente aceites e amplamente utilizados quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="9de6a-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="9de6a-197">Utilize maiúsculas para abreviar.</span><span class="sxs-lookup"><span data-stu-id="9de6a-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="9de6a-198">Utilize maiúsculas para siglas curtas (de duas letras) e inicialismos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="9de6a-199">Utilize `CamelCase` para siglas e rubricas mais longas (três ou mais letras).</span><span class="sxs-lookup"><span data-stu-id="9de6a-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-200">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="9de6a-201">Name</span><span class="sxs-lookup"><span data-stu-id="9de6a-201">Name</span></span> | <span data-ttu-id="9de6a-202">Descrição</span><span class="sxs-lookup"><span data-stu-id="9de6a-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="9de6a-203">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-203">☑</span></span> | `X` | <span data-ttu-id="9de6a-204">Abreviatura bem entendida para "aplicar uma transformação $X$"</span><span class="sxs-lookup"><span data-stu-id="9de6a-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="9de6a-205">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-205">☑</span></span> | `CNOT` | <span data-ttu-id="9de6a-206">Abreviatura bem compreendida para "controlled-NOT"</span><span class="sxs-lookup"><span data-stu-id="9de6a-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="9de6a-207">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="9de6a-208">Abreviação não deve estar dentro `CamelCase` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="9de6a-209">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="9de6a-210">O inicialismo comum "QFT" aparece como parte de um nome de longa forma.</span><span class="sxs-lookup"><span data-stu-id="9de6a-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="9de6a-211">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-211">☑</span></span> | `QFT` | <span data-ttu-id="9de6a-212">O inicialismo comum "QFT" aparece como parte de um nome abreviado.</span><span class="sxs-lookup"><span data-stu-id="9de6a-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="9de6a-213">Substantivos próprios em nomes</span><span class="sxs-lookup"><span data-stu-id="9de6a-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="9de6a-214">Enquanto na física é comum nomear coisas depois da primeira pessoa a publicar sobre elas, a maioria dos não-físicos não estão familiarizados com os nomes de todos e toda a história.</span><span class="sxs-lookup"><span data-stu-id="9de6a-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="9de6a-215">Confiar demasiado na nomeação de convenções da física pode, assim, colocar uma barreira substancial à entrada, uma vez que os utilizadores de outras origens devem aprender um grande número de nomes aparentemente opacos para utilizar operações e conceitos comuns.</span><span class="sxs-lookup"><span data-stu-id="9de6a-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="9de6a-216">Assim, recomendamos que, sempre que razoáveis, substantivos comuns que descrevem um conceito sejam adotados com forte preferência pelos substantivos adequados que descrevem a história da publicação de um conceito.</span><span class="sxs-lookup"><span data-stu-id="9de6a-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="9de6a-217">Como exemplo particular, as operações de SWAP e NOT controladas com singly são muitas vezes chamadas de operações "Fredkin" e "Toffoli" na literatura académica, mas são identificadas em Q# principalmente como `CSWAP` e `CCNOT` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="9de6a-218">Em ambos os casos, os comentários de documentação da API fornecem nomes sinónimos baseados em substantivos adequados, juntamente com todas as citações apropriadas.</span><span class="sxs-lookup"><span data-stu-id="9de6a-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="9de6a-219">Esta preferência é especialmente importante dado que algum uso de substantivos adequados será sempre necessário - Q# segue a tradição definida por muitas línguas clássicas, por exemplo, e refere-se a `Bool` tipos em referência à lógica booleana, que por sua vez é nomeado em homenagem a George Boole.</span><span class="sxs-lookup"><span data-stu-id="9de6a-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="9de6a-220">Alguns conceitos quânticos são igualmente nomeados de forma semelhante, incluindo o `Pauli` tipo incorporado à língua Q#</span><span class="sxs-lookup"><span data-stu-id="9de6a-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="9de6a-221">Minimizando a utilização de substantivos adequados onde tal utilização não é essencial, reduzimos o impacto em que os substantivos adequados não podem ser razoavelmente evitados.</span><span class="sxs-lookup"><span data-stu-id="9de6a-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-222">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="9de6a-223">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-223">We suggest:</span></span>

- <span data-ttu-id="9de6a-224">Evite a utilização de substantivos adequados em nomes.</span><span class="sxs-lookup"><span data-stu-id="9de6a-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-225">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="9de6a-226">Conversões de tipo</span><span class="sxs-lookup"><span data-stu-id="9de6a-226">Type Conversions</span></span> ###

<span data-ttu-id="9de6a-227">Uma vez que Q# é uma linguagem forte e estática dactilografada, um valor de um tipo só pode ser usado como um valor de outro tipo usando uma chamada explícita para uma função de conversão de tipo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="9de6a-228">Isto contrasta com as línguas que permitem que os valores mudem de forma implícita (por exemplo: promoção do tipo), ou através do casting.</span><span class="sxs-lookup"><span data-stu-id="9de6a-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="9de6a-229">Como resultado, as funções de conversão de tipo desempenham um papel importante no desenvolvimento da biblioteca Q# e compreendem uma das decisões mais comummente encontradas sobre nomeação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="9de6a-230">Notamos, no entanto, que, uma vez que as conversões de tipo são sempre _determinísticas,_ podem ser escritas como funções e, portanto, enquadrar-se nos conselhos acima referidos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="9de6a-231">Em particular, sugerimos que as funções de conversão de tipo nunca devem ser nomeadas como verbos (por exemplo: `ConvertToX` ) ou frases preposicionais advérbios ( `ToX` ), mas devem ser nomeadas como frases preposicionais adjetivas que indiquem a fonte e os tipos de destino `XAsY` ().</span><span class="sxs-lookup"><span data-stu-id="9de6a-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="9de6a-232">Ao enumerar os tipos de matriz em nomes de funções de conversão de tipo, recomendamos a abreviatura `Arr` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="9de6a-233">Excluindo circunstâncias excecionais, recomendamos que todas as funções de conversão do tipo sejam nomeadas usando `As` para que possam ser rapidamente identificadas.</span><span class="sxs-lookup"><span data-stu-id="9de6a-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-234">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-235">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-235">We suggest:</span></span>

- <span data-ttu-id="9de6a-236">Se uma função converter um valor de tipo `X` para um valor de `Y` tipo, utilize o nome ou `AsY` `XAsY` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-237">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="9de6a-238">Name</span><span class="sxs-lookup"><span data-stu-id="9de6a-238">Name</span></span> | <span data-ttu-id="9de6a-239">Descrição</span><span class="sxs-lookup"><span data-stu-id="9de6a-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="9de6a-240">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="9de6a-241">A preposição "a" resulta numa frase verbo, indicando uma operação e não uma função.</span><span class="sxs-lookup"><span data-stu-id="9de6a-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="9de6a-242">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="9de6a-243">O tipo de entrada não é claro a partir do nome da função.</span><span class="sxs-lookup"><span data-stu-id="9de6a-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="9de6a-244">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="9de6a-245">Os tipos de entrada e saída aparecem na ordem errada.</span><span class="sxs-lookup"><span data-stu-id="9de6a-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="9de6a-246">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="9de6a-247">Tanto os tipos de entrada como os tipos de saída são claros.</span><span class="sxs-lookup"><span data-stu-id="9de6a-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="9de6a-248">Nomes privados ou internos</span><span class="sxs-lookup"><span data-stu-id="9de6a-248">Private or Internal Names</span></span> ###

<span data-ttu-id="9de6a-249">Em muitos casos, um nome destina-se estritamente a ser usado internamente para uma biblioteca ou projeto, e não é uma parte garantida da API oferecida por uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9de6a-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="9de6a-250">É útil indicar claramente que é esse o caso quando se marcam funções e operações para que as dependências acidentais do código interno sejam tornadas óbvias.</span><span class="sxs-lookup"><span data-stu-id="9de6a-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="9de6a-251">Se uma operação ou função não se destinar a uma utilização direta, mas deve ser utilizada por um callable correspondente que atue por aplicação parcial, considere utilizar um nome que comece `_` pelo callable que é parcialmente aplicado.</span><span class="sxs-lookup"><span data-stu-id="9de6a-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-252">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-253">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-253">We suggest:</span></span>

- <span data-ttu-id="9de6a-254">Quando uma função, operação ou tipo definido pelo utilizador não faz parte da API pública para uma biblioteca ou programa Q#, certifique-se de que o seu nome começa com um sublinhado de liderança `_` ( ).</span><span class="sxs-lookup"><span data-stu-id="9de6a-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-255">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="9de6a-256">Name</span><span class="sxs-lookup"><span data-stu-id="9de6a-256">Name</span></span> | <span data-ttu-id="9de6a-257">Descrição</span><span class="sxs-lookup"><span data-stu-id="9de6a-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="9de6a-258">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-258">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="9de6a-259">O sublinhado `_` não deve aparecer no final do nome.</span><span class="sxs-lookup"><span data-stu-id="9de6a-259">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="9de6a-260">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-260">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="9de6a-261">O sublinhado `_` no início indica claramente que esta operação se destina apenas a uso interno.</span><span class="sxs-lookup"><span data-stu-id="9de6a-261">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="9de6a-262">Variantes</span><span class="sxs-lookup"><span data-stu-id="9de6a-262">Variants</span></span> ###

<span data-ttu-id="9de6a-263">Embora esta limitação possa não persistir em futuras versões de Q#, é atualmente o caso de que muitas vezes haverá grupos de operações ou funções relacionadas que se distinguem pelos quais os functores apoiam os seus inputs, ou pelos tipos concretos dos seus argumentos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="9de6a-264">Estes grupos podem ser distinguidos usando o mesmo nome raiz, seguidos por uma ou duas letras que indicam a sua variante.</span><span class="sxs-lookup"><span data-stu-id="9de6a-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="9de6a-265">Sufixo</span><span class="sxs-lookup"><span data-stu-id="9de6a-265">Suffix</span></span> | <span data-ttu-id="9de6a-266">Significado</span><span class="sxs-lookup"><span data-stu-id="9de6a-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="9de6a-267">Input esperado para apoiar`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="9de6a-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="9de6a-268">Input esperado para apoiar`Controlled`</span><span class="sxs-lookup"><span data-stu-id="9de6a-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="9de6a-269">Entrada esperada para apoiar `Controlled` e`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="9de6a-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="9de6a-270">As inputs ou as inputs são de tipo`Int`</span><span class="sxs-lookup"><span data-stu-id="9de6a-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="9de6a-271">As inputs ou as inputs são de tipo`Double`</span><span class="sxs-lookup"><span data-stu-id="9de6a-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="9de6a-272">As inputs ou as inputs são de tipo`BigInt`</span><span class="sxs-lookup"><span data-stu-id="9de6a-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="9de6a-273">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-274">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-274">We suggest:</span></span>

- <span data-ttu-id="9de6a-275">Se uma função ou operação não estiver relacionada com funções ou operações semelhantes pelos tipos e suporte do functor das suas inputs, não utilize um sufixo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="9de6a-276">Se uma função ou operação estiver relacionada com funções ou operações semelhantes pelos tipos e suporte functor das suas inputs, utilize sufixos como na tabela acima para distinguir variantes.</span><span class="sxs-lookup"><span data-stu-id="9de6a-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-277">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="9de6a-278">Argumentos e Variáveis</span><span class="sxs-lookup"><span data-stu-id="9de6a-278">Arguments and Variables</span></span> ###

<span data-ttu-id="9de6a-279">Um objetivo chave do código Q# para uma função ou operação é que seja facilmente lido e compreendido.</span><span class="sxs-lookup"><span data-stu-id="9de6a-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="9de6a-280">Da mesma forma, os nomes de inputs e argumentos de tipo devem comunicar como uma função ou argumento será usado uma vez fornecido.</span><span class="sxs-lookup"><span data-stu-id="9de6a-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="9de6a-281">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-282">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-282">We suggest:</span></span>

- <span data-ttu-id="9de6a-283">Para todos os nomes variáveis e de entrada, utilize `pascalCase` em forte preferência `CamelCase` `snake_case` para, ou `ANGRY_CASE` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="9de6a-284">Os nomes de entrada devem ser descritivos; evitar um ou dois nomes de letras sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="9de6a-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="9de6a-285">As operações e as funções que aceitam exatamente um tipo de argumento devem denotar esse tipo de argumento quando o `T` seu papel é óbvio.</span><span class="sxs-lookup"><span data-stu-id="9de6a-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="9de6a-286">Se uma função ou operação tiver argumentos de vários tipos, ou se o papel de um único tipo de argumento não for óbvio, considere usar uma palavra capitalizada curta prefaciada por `T` (por exemplo: `TOutput` ) para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="9de6a-287">Não inclua nomes de tipo em nomes de argumentos e variáveis; esta informação pode e deve ser fornecida pelo seu ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="9de6a-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="9de6a-288">Denote tipos escalar pelos seus nomes literais (e tipos de `flagQubit` matriz por um plural `measResults` ).</span><span class="sxs-lookup"><span data-stu-id="9de6a-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="9de6a-289">Para conjuntos de qubits em particular, considere denotar tais tipos por `Register` onde o nome se refere a uma sequência de qubits que estão intimamente relacionados de alguma forma.</span><span class="sxs-lookup"><span data-stu-id="9de6a-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="9de6a-290">As variáveis utilizadas como índices em matrizes devem começar `idx` e devem ser singulares (por exemplo: `things[idxThing]` ).</span><span class="sxs-lookup"><span data-stu-id="9de6a-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="9de6a-291">Em especial, evite misé-lo-de-letra como índices; considerar usar `idx` no mínimo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="9de6a-292">As variáveis utilizadas para conter os comprimentos das matrizes devem começar `n` e devem ser pluralizadas (por exemplo: `nThings` ).</span><span class="sxs-lookup"><span data-stu-id="9de6a-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-293">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="9de6a-294">Itens nomeados por tipo definido do utilizador</span><span class="sxs-lookup"><span data-stu-id="9de6a-294">User Defined Type Named Items</span></span> ###

<span data-ttu-id="9de6a-295">Os itens nomeados em tipos definidos pelo utilizador devem ser nomeados como `CamelCase` , mesmo em entrada para construtores UDT.</span><span class="sxs-lookup"><span data-stu-id="9de6a-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="9de6a-296">Isto ajuda a separar claramente os itens nomeados de referências a variáveis de âmbito local quando se utiliza a notação acessónica (por exemplo: `callable::Apply` ) ou notação de cópia e atualização `set arr w/= Data <- newData` ().</span><span class="sxs-lookup"><span data-stu-id="9de6a-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-297">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-298">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-298">We suggest:</span></span>

- <span data-ttu-id="9de6a-299">Os itens nomeados em construtores uDT devem ser nomeados como `CamelCase` ; isto é, devem começar com uma maiúscula inicial.</span><span class="sxs-lookup"><span data-stu-id="9de6a-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="9de6a-300">Os itens nomeados que resolvem as operações devem ser nomeados como fases verbo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="9de6a-301">Os itens nomeados que não se resolvem às operações devem ser nomeados como frases de substantivos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="9de6a-302">Para os UDTs que encerram as operações, um único item chamado `Apply` deve ser definido.</span><span class="sxs-lookup"><span data-stu-id="9de6a-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-303">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="9de6a-304">Fragmento de código</span><span class="sxs-lookup"><span data-stu-id="9de6a-304">Snippet</span></span> | <span data-ttu-id="9de6a-305">Descrição</span><span class="sxs-lookup"><span data-stu-id="9de6a-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="9de6a-306">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="9de6a-307">O nome `Apply` é uma `CamelCase` frase verbo formatada, sugerindo que o item nomeado é uma operação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="9de6a-308">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="9de6a-309">Os itens nomeados devem começar com uma letra maiúscula inicial.</span><span class="sxs-lookup"><span data-stu-id="9de6a-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="9de6a-310">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="9de6a-311">Os itens nomeados que se resolvem com as funções devem ser nomeados como frases de substantivo, e não como frases verbos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="9de6a-312">Convenções de Entrada</span><span class="sxs-lookup"><span data-stu-id="9de6a-312">Input Conventions</span></span> ##

<span data-ttu-id="9de6a-313">Quando um desenvolvedor chama a uma operação ou função, as várias inputs para essa operação ou função devem ser especificadas numa determinada ordem, aumentando a carga cognitiva que um desenvolvedor enfrenta para fazer uso de uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9de6a-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="9de6a-314">Em particular, a tarefa de lembrar as encomendas de entrada é muitas vezes uma distração da tarefa em questão: programar uma implementação de um algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="9de6a-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="9de6a-315">Embora o apoio rico do IDE possa mitigar isso em grande medida, um bom design e aadesão a convenções comuns também podem ajudar a minimizar a carga cognitiva imposta por uma API.</span><span class="sxs-lookup"><span data-stu-id="9de6a-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="9de6a-316">Sempre que possível, pode ser útil reduzir o número de inputs esperados por uma operação ou função, de modo que o papel de cada entrada seja mais imediatamente óbvio tanto para os desenvolvedores que ligam para essa operação ou função, como para os desenvolvedores que lêem esse código mais tarde.</span><span class="sxs-lookup"><span data-stu-id="9de6a-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="9de6a-317">Especialmente quando não é possível ou razoável reduzir o número de argumentos para uma operação ou função, é importante ter uma ordem consistente que minimize a surpresa que um utilizador enfrenta ao prever a ordem dos inputs.</span><span class="sxs-lookup"><span data-stu-id="9de6a-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="9de6a-318">Recomendamos uma convenção de encomenda de entrada que deriva em grande parte da reflexão da aplicação parcial como uma generalização da currying f(x, y) ≤ f(x)(y).</span><span class="sxs-lookup"><span data-stu-id="9de6a-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="9de6a-319">Assim, a aplicação parcial dos primeiros argumentos deve resultar num callable que seja útil por si só sempre que isso seja razoável.</span><span class="sxs-lookup"><span data-stu-id="9de6a-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="9de6a-320">Seguindo este princípio, considere a utilização da seguinte ordem de argumentação:</span><span class="sxs-lookup"><span data-stu-id="9de6a-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="9de6a-321">Argumentos clássicos não-insensíveis, tais como ângulos, vetores de poderes, etc.</span><span class="sxs-lookup"><span data-stu-id="9de6a-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="9de6a-322">Argumentos insensíveis (funções e argumentos).</span><span class="sxs-lookup"><span data-stu-id="9de6a-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="9de6a-323">Se ambas as funções e operações forem tomadas como argumentos, considere a colocação de operações após funções.</span><span class="sxs-lookup"><span data-stu-id="9de6a-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="9de6a-324">As coleções agiram por argumentos insensíveis de forma semelhante `Map` a, `Iter` , e `Enumerate` `Fold` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="9de6a-325">Argumentos qubit usados como controlos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="9de6a-326">Argumentos qubit usados como alvos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="9de6a-327">Considere uma operação de utilização na estimativa de `ApplyPhaseEstimationIteration` fase que toma um ângulo e um oráculo, passa o ângulo para modificar por uma variedade de `Rz` diferentes fatores de escala, e, em seguida, controla as aplicações do oráculo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="9de6a-328">Ordenamos os inputs da `ApplyPhaseEstimationIteration` seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9de6a-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

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
<span data-ttu-id="9de6a-329">Como um caso especial de minimização surpresa, algumas funções e operações imitam o comportamento dos functors embutidos `Adjoint` e `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="9de6a-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="9de6a-330">Por exemplo, `ControlledOnInt<'T>` tem tipo , tal que age como o functor, mas na condição de que o registo de controlo `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` `ControlledOnInt<Qubit[]>(5, _)` `Controlled` represente o estado $\ket {5} = \ket {101} $.</span><span class="sxs-lookup"><span data-stu-id="9de6a-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="9de6a-331">Assim, um desenvolvedor espera que as inputs `ControlledOnInt` coloquem o callable sendo transformado por último, e que a operação resultante tome como sua entrada `(Qubit[], 'T)` --- a mesma ordem seguida pela saída do `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="9de6a-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-332">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-333">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-333">We suggest:</span></span>

- <span data-ttu-id="9de6a-334">Utilize pedidos de entrada consistentes com a utilização da aplicação parcial.</span><span class="sxs-lookup"><span data-stu-id="9de6a-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="9de6a-335">Utilize pedidos de entrada consistentes com functores incorporados.</span><span class="sxs-lookup"><span data-stu-id="9de6a-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="9de6a-336">Coloque todas as inputs clássicas antes de qualquer entrada quântica.</span><span class="sxs-lookup"><span data-stu-id="9de6a-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-337">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="9de6a-338">Convenções de Documentação</span><span class="sxs-lookup"><span data-stu-id="9de6a-338">Documentation Conventions</span></span> ##

<span data-ttu-id="9de6a-339">O idioma Q# permite anexar documentação a operações, funções e tipos definidos pelo utilizador através da utilização de comentários de documentação especialmente formatados.</span><span class="sxs-lookup"><span data-stu-id="9de6a-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="9de6a-340">Denotados por triplos cortes , estes comentários de `///` documentação são pequenos documentos [de Markdown com sabor do DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) que podem ser usados para descrever o propósito de cada operação, função e tipo definido pelo utilizador, o que as inputs cada espera, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="9de6a-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="9de6a-341">O compilador fornecido com o Kit de Desenvolvimento Quântico extrai estes comentários e usa-os para ajudar a escrever documentação semelhante à de https://docs.microsoft.com/quantum .</span><span class="sxs-lookup"><span data-stu-id="9de6a-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="9de6a-342">Da mesma forma, o servidor de idiomas fornecido com o Kit de Desenvolvimento Quântico utiliza estes comentários para fornecer ajuda aos utilizadores quando pairam sobre símbolos no seu código Q#.</span><span class="sxs-lookup"><span data-stu-id="9de6a-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="9de6a-343">Fazer uso de comentários de documentação pode, assim, ajudar os utilizadores a fazer sentido do código, fornecendo uma referência útil para detalhes que não são facilmente expressos usando as outras convenções deste documento.</span><span class="sxs-lookup"><span data-stu-id="9de6a-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="9de6a-344">
    [Referência de sintaxe de comentários de documentação](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="9de6a-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span></span></div>

<span data-ttu-id="9de6a-345">Para utilizar eficazmente esta funcionalidade para ajudar os utilizadores, recomendamos que tenha algumas coisas em mente à medida que escreve comentários de documentação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-346">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="9de6a-347">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-347">We suggest:</span></span>

- <span data-ttu-id="9de6a-348">Cada função pública, operação e tipo definido pelo utilizador devem ser imediatamente precedidos por um comentário de documentação.</span><span class="sxs-lookup"><span data-stu-id="9de6a-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="9de6a-349">No mínimo, cada comentário de documentação deve incluir as seguintes secções:</span><span class="sxs-lookup"><span data-stu-id="9de6a-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="9de6a-350">Resumo</span><span class="sxs-lookup"><span data-stu-id="9de6a-350">Summary</span></span>
    - <span data-ttu-id="9de6a-351">Entrada</span><span class="sxs-lookup"><span data-stu-id="9de6a-351">Input</span></span>
    - <span data-ttu-id="9de6a-352">Saída (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="9de6a-352">Output (if applicable)</span></span>
- <span data-ttu-id="9de6a-353">Certifique-se de que todos os resumos são duas frases ou menos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="9de6a-354">Se for necessário mais espaço, forneça uma `# Description` secção imediatamente a seguir com detalhes `# Summary` completos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="9de6a-355">Quando razoável, não inclua matemática em resumos, uma vez que nem todos os clientes apoiam a notação TeX em resumos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="9de6a-356">Note que ao escrever documentos de prosa (por exemplo, TeX ou Markdown), pode ser preferível utilizar comprimentos de linha mais longos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="9de6a-357">Forneça todas as expressões matemáticas relevantes na `# Description` secção.</span><span class="sxs-lookup"><span data-stu-id="9de6a-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="9de6a-358">Ao descrever as inputs, não repita os tipos de cada entrada, uma vez que estas podem ser inferidas pelo compilador e correr o risco de introduzir inconsistência.</span><span class="sxs-lookup"><span data-stu-id="9de6a-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="9de6a-359">Forneça exemplos conforme apropriado, cada um na sua própria `# Example` secção.</span><span class="sxs-lookup"><span data-stu-id="9de6a-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="9de6a-360">Descreva brevemente cada exemplo antes de listar o código.</span><span class="sxs-lookup"><span data-stu-id="9de6a-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="9de6a-361">Cite todas as publicações académicas relevantes (por exemplo: trabalhos, procedimentos, posts de bloge implementações alternativas) numa `# References` secção como uma lista de links com balas.</span><span class="sxs-lookup"><span data-stu-id="9de6a-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="9de6a-362">Certifique-se de que, sempre que possível, todas as ligações de citação são para identificadores permanentes e imutáveis (DOIs ou números arXiv versados).</span><span class="sxs-lookup"><span data-stu-id="9de6a-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="9de6a-363">Quando uma operação ou função estiver relacionada com outras operações ou funções por variantes de functor, enumerar outras variantes como balas na `# See Also` secção.</span><span class="sxs-lookup"><span data-stu-id="9de6a-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="9de6a-364">Deixe uma linha de comentários em branco entre as secções de nível 1 ( `/// #` ), mas não deixe uma linha em branco entre as secções de nível 2 ( `/// ##` ).</span><span class="sxs-lookup"><span data-stu-id="9de6a-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-365">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="9de6a-366">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-366">☑</span></span> ####

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

## <a name="formatting-conventions"></a><span data-ttu-id="9de6a-367">Convenções de Formatação</span><span class="sxs-lookup"><span data-stu-id="9de6a-367">Formatting Conventions</span></span> ##

<span data-ttu-id="9de6a-368">Além das sugestões anteriores, é útil ajudar a tornar o código o mais legível possível para usar regras de formatação consistentes.</span><span class="sxs-lookup"><span data-stu-id="9de6a-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="9de6a-369">Tais regras de formatação por natureza tendem a ser um pouco arbitrárias e fortemente até estética seletiva.</span><span class="sxs-lookup"><span data-stu-id="9de6a-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="9de6a-370">No entanto, recomendamos a manutenção de um conjunto consistente de convenções de formatação dentro de um grupo de colaboradores, e especialmente para grandes projetos Q# como o próprio Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="9de6a-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="9de6a-371">Estas regras podem ser aplicadas automaticamente utilizando a ferramenta de formatação integrada com o compilador Q#.</span><span class="sxs-lookup"><span data-stu-id="9de6a-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="9de6a-372">Orientação</span><span class="sxs-lookup"><span data-stu-id="9de6a-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="9de6a-373">Sugerimos:</span><span class="sxs-lookup"><span data-stu-id="9de6a-373">We suggest:</span></span>

- <span data-ttu-id="9de6a-374">Utilize quatro espaços em vez de separadores para portabilidade.</span><span class="sxs-lookup"><span data-stu-id="9de6a-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="9de6a-375">Por exemplo, no Código VS:</span><span class="sxs-lookup"><span data-stu-id="9de6a-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="9de6a-376">Embrulho de linha em 79 caracteres onde razoável.</span><span class="sxs-lookup"><span data-stu-id="9de6a-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="9de6a-377">Utilize espaços em torno de operadores binários.</span><span class="sxs-lookup"><span data-stu-id="9de6a-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="9de6a-378">Utilize espaços em ambos os lados dos cólons utilizados para anotações de tipo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="9de6a-379">Utilize um único espaço após as vírgulas utilizadas em matriz e tuple literal (por exemplo: em inputs para funções e operações).</span><span class="sxs-lookup"><span data-stu-id="9de6a-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="9de6a-380">Não utilize espaços após função, funcionamento ou nomes UDT, ou após as `@` declarações de atributos.</span><span class="sxs-lookup"><span data-stu-id="9de6a-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="9de6a-381">Cada declaração de atributo deve estar na sua própria linha.</span><span class="sxs-lookup"><span data-stu-id="9de6a-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="9de6a-382">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9de6a-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="9de6a-383">Fragmento de código</span><span class="sxs-lookup"><span data-stu-id="9de6a-383">Snippet</span></span> | <span data-ttu-id="9de6a-384">Descrição</span><span class="sxs-lookup"><span data-stu-id="9de6a-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="9de6a-385">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="9de6a-386">Utilize espaços em torno de operadores binários.</span><span class="sxs-lookup"><span data-stu-id="9de6a-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="9de6a-387">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="9de6a-388">Utilize espaços em torno de cólons de anotação tipo.</span><span class="sxs-lookup"><span data-stu-id="9de6a-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="9de6a-389">☑</span><span class="sxs-lookup"><span data-stu-id="9de6a-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="9de6a-390">Os itens em tuple de entrada são corretamente espaçados para a legibilidade.</span><span class="sxs-lookup"><span data-stu-id="9de6a-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="9de6a-391">☒</span><span class="sxs-lookup"><span data-stu-id="9de6a-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="9de6a-392">Os espaços devem ser suprimidos após a função, operação ou nomes uDT.</span><span class="sxs-lookup"><span data-stu-id="9de6a-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

