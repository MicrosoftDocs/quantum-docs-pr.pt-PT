---
title: Especificação de esquema de Broombridge (ver 0.2)
description: Detalha as especificações do esquema de química quântica de Broombridge v0.2 para a biblioteca de química quântica da Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8d26b56d88f365144510692466bfffc7feb71d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854068"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="a34e9-103">Especificação de Broombridge v0.2</span><span class="sxs-lookup"><span data-stu-id="a34e9-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="a34e9-104">As palavras-chave "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHOULD", "SHOULD", "SHOULD", "RECOMMENDED", "MAY" e "OPTIONAL" neste documento devem ser interpretadas como descrito no [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="a34e9-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="a34e9-105">Qualquer barra lateral com os títulos "NOTA", "INFORMAÇÃO" ou "AVISO" é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="a34e9-106">Introdução</span><span class="sxs-lookup"><span data-stu-id="a34e9-106">Introduction</span></span> ##

<span data-ttu-id="a34e9-107">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-107">This section is informative.</span></span>

<span data-ttu-id="a34e9-108">Os documentos de Broombridge destinam-se a comunicar casos de problemas de simulação na química quântica para processamento utilizando simulação quântica e cabos de ferramentas de programação.</span><span class="sxs-lookup"><span data-stu-id="a34e9-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="a34e9-109">Serialização</span><span class="sxs-lookup"><span data-stu-id="a34e9-109">Serialization</span></span> ##

<span data-ttu-id="a34e9-110">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-110">This section is normative.</span></span>

<span data-ttu-id="a34e9-111">Um documento de Broombridge DEVE ser serializado como um [documento YAML 1.2](http://yaml.org/spec/) que representa um objeto JSON, conforme descrito na secção [RFC 4627](https://tools.ietf.org/html/rfc4627) 2.2.</span><span class="sxs-lookup"><span data-stu-id="a34e9-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="a34e9-112">O objeto serializado para YAML MUST tem um `"$schema"` imóvel cujo valor é `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` , e DEVE ser válido de acordo com as especificações do projecto-06 do JSON Schema [[1,](https://tools.ietf.org/html/draft-wright-json-schema-01) [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="a34e9-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="a34e9-113">Para o restante desta especificação, "o objeto Broombridge" refere-se ao objeto JSON desseserializado a partir de um documento YAML de Broombridge.</span><span class="sxs-lookup"><span data-stu-id="a34e9-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="a34e9-114">Salvo indicação em contrário, os objetos NÃO DEVEM ter propriedades adicionais para além das especificadas explicitamente neste documento.</span><span class="sxs-lookup"><span data-stu-id="a34e9-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="a34e9-115">Definições Adicionais</span><span class="sxs-lookup"><span data-stu-id="a34e9-115">Additional Definitions</span></span> ##

<span data-ttu-id="a34e9-116">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="a34e9-117">Objetos de quantidade</span><span class="sxs-lookup"><span data-stu-id="a34e9-117">Quantity Objects</span></span> ###

<span data-ttu-id="a34e9-118">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-118">This section is normative.</span></span>

<span data-ttu-id="a34e9-119">Um _objeto de quantidade_ é um objeto JSON, e DEVE ter uma propriedade cujo valor é um dos `units` valores permitidos listados na Tabela 1.</span><span class="sxs-lookup"><span data-stu-id="a34e9-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="a34e9-120">Um objeto de quantidade é um _objeto de quantidade simples_ se tiver uma única propriedade `value` além da sua `units` propriedade.</span><span class="sxs-lookup"><span data-stu-id="a34e9-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="a34e9-121">O valor do `value` imóvel DEVE ser um número.</span><span class="sxs-lookup"><span data-stu-id="a34e9-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="a34e9-122">Um objeto de quantidade é um _objeto de quantidade limitado_ se tiver as propriedades e `lower` `upper` além da sua `units` propriedade.</span><span class="sxs-lookup"><span data-stu-id="a34e9-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="a34e9-123">Os valores do `lower` e propriedades DEVEM ser `upper` números.</span><span class="sxs-lookup"><span data-stu-id="a34e9-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="a34e9-124">Um objeto de quantidade limitado pode ter uma propriedade `value` cujo valor é um número.</span><span class="sxs-lookup"><span data-stu-id="a34e9-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="a34e9-125">Um objeto de quantidade é um _objeto de quantidade de matriz escassa_ se tiver a propriedade e uma propriedade `format` `values` além da sua `units` propriedade.</span><span class="sxs-lookup"><span data-stu-id="a34e9-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="a34e9-126">O valor de `format` MUST é a `sparse` corda.</span><span class="sxs-lookup"><span data-stu-id="a34e9-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="a34e9-127">O valor do `values` imóvel DEVE ser um conjunto.</span><span class="sxs-lookup"><span data-stu-id="a34e9-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="a34e9-128">Cada elemento de `values` MUST é uma matriz que representa os índices e o valor da quantidade de matriz escassa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="a34e9-129">Os índices para cada elemento de um objeto de quantidade de matriz escassa DEVEM ser únicos em todo o objeto de quantidade de matriz escassa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="a34e9-130">Se um índice estiver presente com um valor de `0` , um parser MUST tratar o objeto de quantidade de matriz escassa de forma idêntica a um objeto de quantidade de matriz escasso no qual esse índice não esteja presente.</span><span class="sxs-lookup"><span data-stu-id="a34e9-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="a34e9-131">Um objeto de quantidade DEVE ser</span><span class="sxs-lookup"><span data-stu-id="a34e9-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="a34e9-132">um simples objeto de quantidade,</span><span class="sxs-lookup"><span data-stu-id="a34e9-132">a simple quantity object,</span></span>
- <span data-ttu-id="a34e9-133">um objeto de quantidade limitado, ou</span><span class="sxs-lookup"><span data-stu-id="a34e9-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="a34e9-134">um objeto de quantidade de matriz escassa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="a34e9-135">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a34e9-135">Examples</span></span> ###

<span data-ttu-id="a34e9-136">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-136">This section is informative.</span></span>

<span data-ttu-id="a34e9-137">Uma quantidade simples representando $1.9844146837 \, \mathrm{Ha}$:</span><span class="sxs-lookup"><span data-stu-id="a34e9-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="a34e9-138">Uma quantidade limitada que representa uma distribuição uniforme durante o intervalo $[-7, -6] \, \mathrm{Ha}$:</span><span class="sxs-lookup"><span data-stu-id="a34e9-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="a34e9-139">Segue-se uma quantidade de matriz escassa com um elemento `[1, 2]` igual e um elemento igual `hello` `[3, 4]` `world` a:</span><span class="sxs-lookup"><span data-stu-id="a34e9-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="a34e9-140">Secção de Formato</span><span class="sxs-lookup"><span data-stu-id="a34e9-140">Format Section</span></span> ##

<span data-ttu-id="a34e9-141">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-141">This section is normative.</span></span>

<span data-ttu-id="a34e9-142">O objeto Broombridge DEVE ter uma propriedade `format` cujo valor é um objeto JSON com uma propriedade chamada `version` .</span><span class="sxs-lookup"><span data-stu-id="a34e9-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="a34e9-143">O `version` imóvel DEVE ter o `"0.2"` valor.</span><span class="sxs-lookup"><span data-stu-id="a34e9-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="a34e9-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a34e9-144">Example</span></span> ###

<span data-ttu-id="a34e9-145">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="a34e9-146">Secção de Descrição de Problemas</span><span class="sxs-lookup"><span data-stu-id="a34e9-146">Problem Description Section</span></span> ##

<span data-ttu-id="a34e9-147">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-147">This section is normative.</span></span>

<span data-ttu-id="a34e9-148">O objeto Broombridge DEVE ter uma propriedade `problem_description` cujo valor é uma matriz JSON.</span><span class="sxs-lookup"><span data-stu-id="a34e9-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="a34e9-149">Cada item no valor da `problem_description` propriedade DEVE ser um objeto JSON descrevendo um conjunto de integrais, conforme descrito no restante desta secção.</span><span class="sxs-lookup"><span data-stu-id="a34e9-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="a34e9-150">No restante desta secção, o termo "objeto de descrição de problemas" refere-se a um item no valor da `problem_description` propriedade do objeto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="a34e9-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="a34e9-151">Cada objeto de descrição de problemas DEVE ter uma propriedade `metadata` cujo valor é um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="a34e9-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="a34e9-152">O valor de `metadata` MAIO é o objeto JSON vazio (isto é, ) ou MAY contém propriedades `{}` adicionais definidas pelo implementor.</span><span class="sxs-lookup"><span data-stu-id="a34e9-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="a34e9-153">Secção Hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="a34e9-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="a34e9-154">Descrição geral</span><span class="sxs-lookup"><span data-stu-id="a34e9-154">Overview</span></span> ####

<span data-ttu-id="a34e9-155">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-155">This section is informative.</span></span>

<span data-ttu-id="a34e9-156">A `hamiltonian` propriedade de cada objeto de descrição de problemas descreve o Hamiltonian para um problema particular de química quântica, enumerando os seus termos de um e dois corpos como conjuntos escassos de números reais.</span><span class="sxs-lookup"><span data-stu-id="a34e9-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="a34e9-157">Os operadores hamiltonianos descritos por cada objeto de descrição de problemas tomar o formulário</span><span class="sxs-lookup"><span data-stu-id="a34e9-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="a34e9-158">$$ H = \sum \_ \{ i,j \} \sum \_ {\sigma\in \\ {\uparrow,\downarrow \\ }} h \_ \{ ij \} \{ a^ \dagger \} \_ {i,\sigma} a \_ {j,\sigma} + \frac {1} {2} \frac \sum \_ \{ i,j,k,l \} \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }} h \_ {ijkl} a^\dagger \_ {i,\sigma} a^\dagger \_ {k,\rho} a \_ {l,\rho} a \_ {j,\sigma}, $$</span><span class="sxs-lookup"><span data-stu-id="a34e9-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="a34e9-159">aqui $h_{ijkl}= (ij|kl)$ na convenção de Mulliken.</span><span class="sxs-lookup"><span data-stu-id="a34e9-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="a34e9-160">Para clareza, o termo de um eletrão é</span><span class="sxs-lookup"><span data-stu-id="a34e9-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="a34e9-161">$$ h_{ij} = \int {\mathrm d}x \psi^\* \_ i(x) \esquerda (\frac {1} {2} \nabla^2 + \soma \_ {A}frac{Z \_ A}{|x-x \_ A|}  \direita) \psi \_ j(x), $$</span><span class="sxs-lookup"><span data-stu-id="a34e9-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="a34e9-162">e o termo de dois eletrões é</span><span class="sxs-lookup"><span data-stu-id="a34e9-162">and the two-electron term is</span></span>

<span data-ttu-id="a34e9-163">$$ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x^2 \psi^ \{ \* \} \_ i(x \_ 1)\psi \_ j(x \_ 1) \frac \{ 1 \} \{ \| x \_ \_ 1 -2 \| \} \psi \_ k^ \{ \* \} (x \_ 2) \psi \_ l(x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="a34e9-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="a34e9-164">Como indicado na nossa descrição da [ `basis_set` propriedade](#basis-set-object) de cada elemento do `integral_sets` imóvel, assumimos explicitamente que as funções de base utilizadas são de valor real.</span><span class="sxs-lookup"><span data-stu-id="a34e9-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="a34e9-165">Isto permite-nos usar as seguintes assimetrias entre os termos para comprimir a representação do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a34e9-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="a34e9-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span><span class="sxs-lookup"><span data-stu-id="a34e9-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="a34e9-167">Conteúdos</span><span class="sxs-lookup"><span data-stu-id="a34e9-167">Contents</span></span> ####

<span data-ttu-id="a34e9-168">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-168">This section is normative.</span></span>

<span data-ttu-id="a34e9-169">Cada objeto de descrição de problemas DEVE ter uma propriedade `hamiltonian` cujo valor é um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="a34e9-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="a34e9-170">O valor da `hamiltonian` propriedade é conhecido como um objeto hamiltoniano, e DEVE ter as propriedades e como descrito no restante desta `one_electron_integrals` `two_electron_integrals` secção.</span><span class="sxs-lookup"><span data-stu-id="a34e9-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="a34e9-171">Cada objeto de descrição de problemas DEVE ter uma propriedade `coulomb_repulsion` cujo valor é um objeto de quantidade simples.</span><span class="sxs-lookup"><span data-stu-id="a34e9-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="a34e9-172">Cada objeto de descrição de problemas DEVE ter uma propriedade `energy_offet` cujo valor é um objeto de quantidade simples.</span><span class="sxs-lookup"><span data-stu-id="a34e9-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="a34e9-173">[NOTA] Os valores `coulomb_repulsion` de e `energy_offet` juntos captam o termo de identidade do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a34e9-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="a34e9-174">Objeto One-Electron Integrals</span><span class="sxs-lookup"><span data-stu-id="a34e9-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="a34e9-175">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-175">This section is normative.</span></span>

<span data-ttu-id="a34e9-176">A `one_electron_integrals` propriedade do objeto Hamiltonian DEVE ser uma quantidade escassa de matriz cujos índices são dois inteiros e cujos valores são números.</span><span class="sxs-lookup"><span data-stu-id="a34e9-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="a34e9-177">Todos os termos devem ter índices `[i, j]` onde `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="a34e9-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="a34e9-178">[NOTA] Isto reflete a simetria que $h_{ij} = h_{ji}$ o que é uma consequência do facto de o Hamiltonian ser hermitiano.</span><span class="sxs-lookup"><span data-stu-id="a34e9-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="a34e9-179">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a34e9-179">Example</span></span> ######

<span data-ttu-id="a34e9-180">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-180">This section is informative.</span></span>

<span data-ttu-id="a34e9-181">A quantidade de matriz escassa que se segue representa o Hamiltonian $$ H = \esquerda (-5,0 (a^ \{ \dagger \} \_ {1,\uparrow} a \_ {1,\uparrow}+a^ \{ \dagger \} \_ {1,\downarrow} a \_ {1,\downarrow}+ 0,17 (a^ \{ \agger \} \_ {2,uparrow arow a a{1\uparrow arow a a{2,uparrow arow a arow a a{2,uparrow arow a\*downrow a a{1,\downarrow} \_ {1,\uparrow}+ a^ \{ \dagger \} \_ {1,\uparrow} a \_ {2,\uparrow}+a^ \{ \dagger \} \_ {2,\downarrow} a \_ {1,\downarrow}+ a^ \{ \dagger \} \_ {1,\downarrow} a \_ {2,\downarrow})\right) \\ \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="a34e9-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="a34e9-182">Broombridge usa indexação baseada em 1.</span><span class="sxs-lookup"><span data-stu-id="a34e9-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="a34e9-183">Objeto Two-Electron Integrals</span><span class="sxs-lookup"><span data-stu-id="a34e9-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="a34e9-184">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-184">This section is normative.</span></span>

<span data-ttu-id="a34e9-185">A `two_electron_integrals` propriedade do objeto Hamiltonian DEVE ser uma quantidade de matriz escassa com uma propriedade adicional chamada `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="a34e9-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="a34e9-186">Cada elemento do valor de `two_electron_integrals` MUST tem quatro índices.</span><span class="sxs-lookup"><span data-stu-id="a34e9-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="a34e9-187">Cada `two_electron_integrals` imóvel DEVE ter uma `index_convention` propriedade.</span><span class="sxs-lookup"><span data-stu-id="a34e9-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="a34e9-188">O valor do `index_convention` imóvel DEVE ser um dos valores permitidos listados no Quadro 1.</span><span class="sxs-lookup"><span data-stu-id="a34e9-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="a34e9-189">Se o valor for `index_convention` `mulliken` , então para cada elemento da quantidade de `two_electron_integrals` matriz escassa, um parser carregando um documento de Broombridge DEVE instantaneamente um termo Hamiltonian igual ao operador de dois eletrões $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, onde $i$, $j$, $k$, e $l$ MUST são inteiros de valor pelo menos 1, e onde $h_{i, j, k, l}$ é o elemento `[i, j, k, l, h(i, j, k, l)]` da quantidade de matriz escassa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="a34e9-190">Assimetrias</span><span class="sxs-lookup"><span data-stu-id="a34e9-190">Symmetries</span></span> ######

<span data-ttu-id="a34e9-191">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-191">This section is normative.</span></span>

<span data-ttu-id="a34e9-192">Se a `index_convention` propriedade de um objeto for igual a , `two_electron_integrals` `mulliken` então se um elemento com índices `[i, j, k, l]` estiver presente, os seguintes índices NÃO devem estar presentes a menos que sejam iguais `[i, j, k, l]` a:</span><span class="sxs-lookup"><span data-stu-id="a34e9-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="a34e9-193">Como a `index_convention` propriedade é um objeto de quantidade escassa, nenhum índice pode ser repetido em diferentes elementos.</span><span class="sxs-lookup"><span data-stu-id="a34e9-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="a34e9-194">Em particular, se um elemento com índices `[i, j, k, l]` estiver presente, nenhum outro elemento pode ter esses índices.</span><span class="sxs-lookup"><span data-stu-id="a34e9-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="a34e9-195">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a34e9-195">Example</span></span> #######

<span data-ttu-id="a34e9-196">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-196">This section is informative.</span></span>

<span data-ttu-id="a34e9-197">O seguinte objeto especifica o Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="a34e9-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="a34e9-198">$$ H = \frac12 \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }}\Biggr( 1.6 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {1,\rho} a \_ {1,\rho} a \_ {1,\rho} a {1,\a^{1,\rho} \_ a \_ \_ {3,\rho} a \_ {2,\sigma}- 0,1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {2,\rho} a \_ {3,\rho} a {3,\sigma}- 0.1 a^{\dagger} \_ {1,\a^a^} \_ {6,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0,1 a^{\dagger} \_ {1,\sigma} {{\dagger} \_ {6,\rho} a \_ {2,\rho} a \_ {3,\sigma} $$ $-0,1 a^{\dagger} \_ {3,sigma\a{\a{{2,\rho} \_ a \_ {6,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {1,\rho} a \_ {6,\sigma}- 0,1 a^{\dagger} \_ {2,\sigma} \_ .\rho} a \_ {6,\rho} a \_ {1,\sigma}- 0,1 a^{\dagger} \_ {2,\sigma} a^{\dagger} \_ {3,\rho} a \_ {1,\rho} a \_ {6,\sigma}\Biggr) \\ \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="a34e9-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a><span data-ttu-id="a34e9-199">Secção inicial do Estado</span><span class="sxs-lookup"><span data-stu-id="a34e9-199">Initial State Section</span></span> ###

<span data-ttu-id="a34e9-200">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-200">This section is normative.</span></span>

<span data-ttu-id="a34e9-201">O `initial_state_suggestion` objeto cujo valor é uma matriz JSON especifica estados quânticos iniciais de interesse para o Hamiltonian especificado.</span><span class="sxs-lookup"><span data-stu-id="a34e9-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="a34e9-202">Cada item no valor da `initial_state_suggestion` propriedade DEVE ser um objeto JSON descrevendo um estado quântico, como descrito no restante desta secção.</span><span class="sxs-lookup"><span data-stu-id="a34e9-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="a34e9-203">No restante desta secção, o termo "objeto de estado" refere-se a um item no valor da `initial_state_suggestion` propriedade do objeto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="a34e9-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="a34e9-204">Objeto de Estado</span><span class="sxs-lookup"><span data-stu-id="a34e9-204">State object</span></span> ####

<span data-ttu-id="a34e9-205">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-205">This section is normative.</span></span>

<span data-ttu-id="a34e9-206">Cada objeto de estado DEVE ter uma `label` propriedade contendo uma corda.</span><span class="sxs-lookup"><span data-stu-id="a34e9-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="a34e9-207">Cada objeto de estado DEVE ter uma `method` propriedade.</span><span class="sxs-lookup"><span data-stu-id="a34e9-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="a34e9-208">O valor do `method` imóvel DEVE ser um dos valores permitidos listados no Quadro 3.</span><span class="sxs-lookup"><span data-stu-id="a34e9-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="a34e9-209">Cada objeto de estado pode ter uma propriedade `energy` cujo valor DEVE ser um objeto de quantidade simples.</span><span class="sxs-lookup"><span data-stu-id="a34e9-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="a34e9-210">Se o valor do `method` imóvel `sparse_multi_configurational` for, o objeto de estado DEVE ter uma `superposition` propriedade contendo um conjunto de estados de base e suas amplitudes não normalizadas.</span><span class="sxs-lookup"><span data-stu-id="a34e9-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="a34e9-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger} \_ {1,\uparrow}a^{\dagger} \_ {2,\uparrow}a^{\dagger} \_ {2,\downarrow})\ket {0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger} \_ {1,\uparrow}a^{\dagger} \_ {2,\uparrow}a^{\dagger} \_ {2,\downarrow})+0.2 (a^{\dagger} \_ {1,\uparrow}a^{\dagger} \_ {3,\uparrow}a^{\dagger} \_ {2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket {0} , $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span><span class="sxs-lookup"><span data-stu-id="a34e9-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="a34e9-212">Se o valor do `method` imóvel `unitary_coupled_cluster` for, o objeto de estado DEVE ter um `cluster_operator` imóvel cujo valor é um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="a34e9-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="a34e9-213">O objeto JSON DEVE ter um `reference_state` imóvel cujo valor é um estado de base.</span><span class="sxs-lookup"><span data-stu-id="a34e9-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="a34e9-214">O objeto JSON pode ter uma `one_body_amplitudes` propriedade cujo valor é uma matriz de operadores de cluster de um corpo e suas amplitudes.</span><span class="sxs-lookup"><span data-stu-id="a34e9-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="a34e9-215">O objeto JSON pode ter uma `two_body_amplitudes` propriedade cujo valor é uma matriz de operadores de cluster de dois corpos e suas amplitudes.</span><span class="sxs-lookup"><span data-stu-id="a34e9-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="a34e9-216">contendo uma série de estados de base e as suas amplitudes não normalizadas.</span><span class="sxs-lookup"><span data-stu-id="a34e9-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="a34e9-217">Por exemplo, o estado $\ \ket{\text{reference}=(a^{\dagger} \_ {1,\uparrow}a^{\dagger} \_ {2,\uparrow}a^{\dagger} \_ {2,\downarrow}\ket {0} , $$</span><span class="sxs-lookup"><span data-stu-id="a34e9-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="a34e9-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}, $$</span><span class="sxs-lookup"><span data-stu-id="a34e9-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="a34e9-219">$$ T = 0,1 a^{\dagger} \_ {3,\uparrow}a \_ {2,\downarrow} + 0,2 a^{\dagger} \_ {2,\uparrow}a \_ {2,\downarrow} - 0,3 a^{\dagger} \_ {1,\uparrow}a^{\dagger} \_ {3,\downarrow}a \_ {3,\uparrow}a \_ {2,\downarrow} $$ é representado por</span><span class="sxs-lookup"><span data-stu-id="a34e9-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="a34e9-220">Objeto de conjunto de base</span><span class="sxs-lookup"><span data-stu-id="a34e9-220">Basis Set Object</span></span> ####

<span data-ttu-id="a34e9-221">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-221">This section is normative.</span></span>

<span data-ttu-id="a34e9-222">Cada objeto de descrição de problemas pode ter uma `basis_set` propriedade.</span><span class="sxs-lookup"><span data-stu-id="a34e9-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="a34e9-223">Se estiver presente, o valor do `basis_set` imóvel DEVE ser um objeto com duas propriedades, `type` e `name` .</span><span class="sxs-lookup"><span data-stu-id="a34e9-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="a34e9-224">As funções de base identificadas pelo valor do `basis_set` imóvel MUST são de valor real.</span><span class="sxs-lookup"><span data-stu-id="a34e9-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="a34e9-225">O pressuposto de que todas as funções de base são valorizados real pode ser relaxado em futuras versões desta especificação.</span><span class="sxs-lookup"><span data-stu-id="a34e9-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="a34e9-226">Tabelas e Listas</span><span class="sxs-lookup"><span data-stu-id="a34e9-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="a34e9-227">Tabela 1.</span><span class="sxs-lookup"><span data-stu-id="a34e9-227">Table 1.</span></span> <span data-ttu-id="a34e9-228">Unidades Físicas Permitidas</span><span class="sxs-lookup"><span data-stu-id="a34e9-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="a34e9-229">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-229">This section is normative.</span></span>

<span data-ttu-id="a34e9-230">Qualquer cadeia que especifique uma unidade DEVE ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="a34e9-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="a34e9-231">Os parsers e produtores DEVEM tratar os seguintes objetos de quantidade simples como equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a34e9-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="a34e9-232">Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="a34e9-232">Table 2.</span></span> <span data-ttu-id="a34e9-233">Convenções de Índice Permitidas</span><span class="sxs-lookup"><span data-stu-id="a34e9-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="a34e9-234">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-234">This section is normative.</span></span>

<span data-ttu-id="a34e9-235">Qualquer cadeia que especifique uma convenção de índice DEVE ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="a34e9-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="a34e9-236">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-236">This section is informative.</span></span>

<span data-ttu-id="a34e9-237">As convenções de índice adicionais podem ser introduzidas em futuras versões desta especificação.</span><span class="sxs-lookup"><span data-stu-id="a34e9-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="a34e9-238">Interpretação das Convenções de Índice</span><span class="sxs-lookup"><span data-stu-id="a34e9-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="a34e9-239">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="a34e9-240">Tabela 3.</span><span class="sxs-lookup"><span data-stu-id="a34e9-240">Table 3.</span></span> <span data-ttu-id="a34e9-241">Métodos permitidos do Estado</span><span class="sxs-lookup"><span data-stu-id="a34e9-241">Allowed State methods</span></span> ###

<span data-ttu-id="a34e9-242">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-242">This section is normative.</span></span>

<span data-ttu-id="a34e9-243">Qualquer cadeia que especifique um método de estado DEVE ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="a34e9-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="a34e9-244">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="a34e9-244">This section is informative.</span></span>

<span data-ttu-id="a34e9-245">Podem ser introduzidos métodos estatais adicionais em futuras versões desta especificação.</span><span class="sxs-lookup"><span data-stu-id="a34e9-245">Additional state methods may be introduced in future versions of this specification.</span></span>
