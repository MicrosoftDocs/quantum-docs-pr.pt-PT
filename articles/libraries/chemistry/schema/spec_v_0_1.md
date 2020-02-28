---
title: Especificação Broombridge Schema (ver 0.1)
description: Detalha as especificações para o esquema de química quântica de Broombridge v0.1 para a biblioteca de química quântica da Microsoft.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906428"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="5f6ed-103">Especificação broombridge v0.1</span><span class="sxs-lookup"><span data-stu-id="5f6ed-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="5f6ed-104">As palavras-chave "MUST", "MUST NOT", "REQUIRED", "DEVE", "NÃO DEVE", "NÃO DEVEM", "RECOMENDADO", "MAIO" e "OPCIONAL" neste documento devem ser interpretadas como descrito no [RFC 2119.](https://tools.ietf.org/html/rfc2119)</span><span class="sxs-lookup"><span data-stu-id="5f6ed-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="5f6ed-105">Qualquer barra lateral com as rubricas "NOTA", "INFORMAÇÃO" ou "AVISO" é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="5f6ed-106">Introdução</span><span class="sxs-lookup"><span data-stu-id="5f6ed-106">Introduction</span></span> ##

<span data-ttu-id="5f6ed-107">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-107">This section is informative.</span></span>

<span data-ttu-id="5f6ed-108">Os documentos de Broombridge destinam-se a comunicar casos de problemas de simulação na química quântica para processamento utilizando cadeias de ferramentas de simulação quântica e programação.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="5f6ed-109">Serialização</span><span class="sxs-lookup"><span data-stu-id="5f6ed-109">Serialization</span></span> ##

<span data-ttu-id="5f6ed-110">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-110">This section is normative.</span></span>

<span data-ttu-id="5f6ed-111">Um documento broombridge DEVE ser serializado como um [documento YAML 1.2](http://yaml.org/spec/) que representa um objeto JSON, conforme descrito na secção 2.2 do [RFC 4627.](https://tools.ietf.org/html/rfc4627)</span><span class="sxs-lookup"><span data-stu-id="5f6ed-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="5f6ed-112">O objeto serializado para o YAML MUST tem uma propriedade `"$schema"` cujo valor seja `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, e DEVE ser válido de acordo com as especificações json schema[[1,](https://tools.ietf.org/html/draft-wright-json-schema-01) [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="5f6ed-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="5f6ed-113">Para o resto desta especificação, "o objeto Broombridge" refere-se ao objeto JSON desserializado a partir de um documento YAML de Broombridge.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="5f6ed-114">Salvo indicação em contrário, os objetos NÃO DEVEM ter propriedades adicionais para além das especificadas explicitamente neste documento.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="5f6ed-115">Definições adicionais</span><span class="sxs-lookup"><span data-stu-id="5f6ed-115">Additional Definitions</span></span> ##

<span data-ttu-id="5f6ed-116">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="5f6ed-117">Objetos de quantidade</span><span class="sxs-lookup"><span data-stu-id="5f6ed-117">Quantity Objects</span></span> ###

<span data-ttu-id="5f6ed-118">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-118">This section is normative.</span></span>

<span data-ttu-id="5f6ed-119">Um _objeto de quantidade_ é um objeto JSON, e MUST tem um `units` de propriedade cujo valor é um dos valores permitidos listados no Quadro 1.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="5f6ed-120">Um objeto de quantidade é um _objeto de quantidade simples_ se tiver uma única propriedade `value` além da sua propriedade `units`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="5f6ed-121">O valor da propriedade `value` DEVE ser um número.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="5f6ed-122">Um objeto de quantidade é um objeto de _quantidade limitado_ se tiver as propriedades `lower` e `upper` além da sua propriedade `units`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="5f6ed-123">Os valores das propriedades `lower` e `upper` devem ser números.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="5f6ed-124">Um objeto de quantidade limitado PODE ter uma propriedade `value` cujo valor é um número.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="5f6ed-125">Um objeto de quantidade é um _objeto de quantidade escassa_ se tiver a propriedade `format` e uma propriedade `values` além da sua propriedade `units`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="5f6ed-126">O valor do `format` DEVE ser a cadeia `sparse`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="5f6ed-127">O valor da propriedade `values` DEVE ser uma matriz.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="5f6ed-128">Cada elemento de `values` DEVE ser um matriz que representa os índices e o valor da escassa quantidade de matriz.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="5f6ed-129">Os índices para cada elemento de um objeto de quantidade escassa de matriz DEVEM ser únicos em todo o objeto de quantidade de matriz escassa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="5f6ed-130">Se um índice estiver presente com um valor de `0`, um parser MUST tratar o objeto de quantidade escassa de matriz de forma idêntica a um objeto de quantidade escassa de matriz em que esse índice não esteja presente.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="5f6ed-131">Um objeto de quantidade DEVE ser</span><span class="sxs-lookup"><span data-stu-id="5f6ed-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="5f6ed-132">um simples objeto de quantidade,</span><span class="sxs-lookup"><span data-stu-id="5f6ed-132">a simple quantity object,</span></span>
- <span data-ttu-id="5f6ed-133">um objeto de quantidade limitado, ou</span><span class="sxs-lookup"><span data-stu-id="5f6ed-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="5f6ed-134">um objeto de quantidade escassa de matriz.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="5f6ed-135">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5f6ed-135">Examples</span></span> ###

<span data-ttu-id="5f6ed-136">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-136">This section is informative.</span></span>

<span data-ttu-id="5f6ed-137">Uma quantidade simples que representa $1.9844146837\,\mathrm{Ha}$:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="5f6ed-138">Uma quantidade limitada que representa uma distribuição uniforme ao longo do intervalo $[-7, -6]\,\mathrm{Ha}$:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="5f6ed-139">Segue-se uma quantidade escassa de matriz com um elemento `[1, 2]` igual a `hello` e um elemento `[3, 4]` igual a `world`:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="5f6ed-140">Secção de Formato</span><span class="sxs-lookup"><span data-stu-id="5f6ed-140">Format Section</span></span> ##

<span data-ttu-id="5f6ed-141">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-141">This section is normative.</span></span>

<span data-ttu-id="5f6ed-142">O objeto broombridge MUST tem uma propriedade `format` cujo valor é um objeto JSON com uma propriedade chamada `version`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="5f6ed-143">A propriedade `version` DEVE ter o valor `"0.1"`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="5f6ed-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5f6ed-144">Example</span></span> ###

<span data-ttu-id="5f6ed-145">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="5f6ed-146">Secção conjuntos integrais</span><span class="sxs-lookup"><span data-stu-id="5f6ed-146">Integral Sets Section</span></span> ##

<span data-ttu-id="5f6ed-147">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-147">This section is normative.</span></span>

<span data-ttu-id="5f6ed-148">O objeto broombridge MUST tem uma propriedade `integral_sets` cujo valor é uma matriz JSON.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="5f6ed-149">Cada item no valor da propriedade `integral_sets` DEVE ser um objeto JSON descrevendo um conjunto de integrais, conforme descrito no restante desta secção.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="5f6ed-150">No restante desta secção, o termo "objeto integral definido" referir-se-á a um item no valor da propriedade `integral_sets` do objeto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="5f6ed-151">Cada objeto conjunto integral MUST tem uma propriedade `metadata` cujo valor é um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="5f6ed-152">O valor de `metadata` pode ser o objeto JSON vazio (isto é, `{}`), ou MAIO contém propriedades adicionais definidas pelo implementador.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="5f6ed-153">Secção Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="5f6ed-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="5f6ed-154">Descrição geral</span><span class="sxs-lookup"><span data-stu-id="5f6ed-154">Overview</span></span> ####

<span data-ttu-id="5f6ed-155">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-155">This section is informative.</span></span>

<span data-ttu-id="5f6ed-156">A propriedade `hamiltonian` de cada objeto conjunto integral descreve o Hamiltonian para um problema particular de química quântica, enumerando os seus termos de um e dois corpos como matrizes escassas de números reais.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="5f6ed-157">Os operadores hamiltonianos descritos por cada objeto conjunto integral tomam a forma</span><span class="sxs-lookup"><span data-stu-id="5f6ed-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="5f6ed-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\\\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i ,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span><span class="sxs-lookup"><span data-stu-id="5f6ed-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="5f6ed-159">aqui $h_{ijkl}= (ijkl)$ na convenção de Mulliken.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="5f6ed-160">Para clareza, o termo um-electrão é</span><span class="sxs-lookup"><span data-stu-id="5f6ed-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="5f6ed-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{;x-x\_A}  \direita) \psi\_j(x), $$</span><span class="sxs-lookup"><span data-stu-id="5f6ed-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="5f6ed-162">e o termo de dois eletrões é</span><span class="sxs-lookup"><span data-stu-id="5f6ed-162">and the two-electron term is</span></span>

<span data-ttu-id="5f6ed-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_(x\_1)\psi\_j(x\_1) \frac\{1\}\|\{ x\_1 -x\_2\|\}\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span><span class="sxs-lookup"><span data-stu-id="5f6ed-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="5f6ed-164">Como notado na nossa descrição da [propriedade`basis_set`](#basis-set-object) de cada elemento da propriedade `integral_sets`, assumimos explicitamente que as funções base utilizadas são de valor real.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="5f6ed-165">Isto permite-nos usar as seguintes simetrias entre os termos para comprimir a representação do Hamiltoniano.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="5f6ed-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="5f6ed-167">Conteúdos</span><span class="sxs-lookup"><span data-stu-id="5f6ed-167">Contents</span></span> ####

<span data-ttu-id="5f6ed-168">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-168">This section is normative.</span></span>

<span data-ttu-id="5f6ed-169">Cada conjunto integral MUST tem uma propriedade `hamiltonian` cujo valor é um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="5f6ed-170">O valor da propriedade `hamiltonian` é conhecido como um objeto hamiltoniano, e MUST tem as propriedades `one_electron_integrals` e `two_electron_integrals` como descrito no restante desta secção.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="5f6ed-171">Um objeto hamiltoniano may também tem uma propriedade `particle_hole_representation`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="5f6ed-172">Se presente, o valor da `particle_hole_representation` DEVE seguir o formato descrito no restante desta secção.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="5f6ed-173">Objeto integral de um eletrão</span><span class="sxs-lookup"><span data-stu-id="5f6ed-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="5f6ed-174">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-174">This section is normative.</span></span>

<span data-ttu-id="5f6ed-175">A propriedade `one_electron_integrals` do objeto hamiltoniano DEVE ser uma quantidade escassa de matriz cujos índices são dois inteiros e cujos valores são números.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="5f6ed-176">Todos os mandatos devem ter índices `[i, j]` onde `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="5f6ed-177">[NOTA] Isto reflete a simetria que $h_{ij} = h_{ji}$ que é uma consequência do facto de o Hamiltoniano ser Hermitiano.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="5f6ed-178">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5f6ed-178">Example</span></span> ######

<span data-ttu-id="5f6ed-179">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-179">This section is informative.</span></span>

<span data-ttu-id="5f6ed-180">A seguinte quantidade de matriz escassa representa o Hamiltonian $$ H = \left (-5.0 (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\\\downarrow})+ 0,17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2 ,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})à direita)\\(\mathrm{Ha}).</span><span class="sxs-lookup"><span data-stu-id="5f6ed-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="5f6ed-181">Broombridge usa índice seleção de 1.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="5f6ed-182">Objeto integral de dois eletrões</span><span class="sxs-lookup"><span data-stu-id="5f6ed-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="5f6ed-183">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-183">This section is normative.</span></span>

<span data-ttu-id="5f6ed-184">A propriedade `two_electron_integrals` do objeto Hamiltonian DEVE ser uma quantidade escassa de matriz com uma propriedade adicional chamada `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="5f6ed-185">Cada elemento do valor do `two_electron_integrals` DEVE tem quatro índices.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="5f6ed-186">Cada `two_electron_integrals` propriedade DEVE ter uma propriedade `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="5f6ed-187">O valor da propriedade `index_convention` DEVE ser um dos valores permitidos enumerados no Quadro 1.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="5f6ed-188">Se o valor da `index_convention` for `mulliken`, então para cada elemento da quantidade de matriz escassa `two_electron_integrals`, um parser carregando um documento broombridge MUST instantaneamente um termo Hamiltonian igual ao operador de dois eletrões $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, onde $i$, $j$, $k$, e $l$ MUST ser inteiros na gama inclusiva de 1 a o número de eletrões especificados pela propriedade `n_electrons` do objeto conjunto integral, e onde $h_{i, j , k, l}$ é o elemento `[i, j, k, l, h(i, j, k, l)]` da quantidade escassa da matriz.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="5f6ed-189">Simetrias</span><span class="sxs-lookup"><span data-stu-id="5f6ed-189">Symmetries</span></span> ######

<span data-ttu-id="5f6ed-190">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-190">This section is normative.</span></span>

<span data-ttu-id="5f6ed-191">Se a propriedade `index_convention` de um objeto `two_electron_integrals` for igual a `mulliken`, então se estiver presente um elemento com índices `[i, j, k, l]`, os seguintes índices não devem estar presentes a menos que sejam iguais a `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="5f6ed-192">Como a propriedade `index_convention` é um objeto de quantidade escassa, nenhum índice pode ser repetido em diferentes elementos.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="5f6ed-193">Em particular, se um elemento com índices `[i, j, k, l]` estiver presente, nenhum outro elemento pode ter esses índices.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="5f6ed-194">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5f6ed-194">Example</span></span> #######

<span data-ttu-id="5f6ed-195">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-195">This section is informative.</span></span>

<span data-ttu-id="5f6ed-196">O seguinte objeto especifica o Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="5f6ed-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="5f6ed-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1,6 a{\dagger}\_{1,\sigma} a^{\dagger}\_{1,rho} a\_{1,rho} a\_{1,sigma}- 0,1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma}\_\_a{\a .\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^\_{\a 6,\rho} um\_{2,\rho} um\_{3,\sigma} $$-0,1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0,1a^\\_a.a ,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,rho} um\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\"\textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="5f6ed-198">Objeto de representação de buraco de partícula</span><span class="sxs-lookup"><span data-stu-id="5f6ed-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="5f6ed-199">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-199">This section is normative.</span></span>

<span data-ttu-id="5f6ed-200">O objeto de representação de buracos de partículas especifica que os integrais armazenados são definidos no que diz respeito à representação de buracos de partículas, onde os operadores de criação e aniquilação descrevem as excitações longe do estado de referência utilizado, como um Hartree. Estado de Fock.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="5f6ed-201">O objeto é OPCIONAL.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="5f6ed-202">Se o objeto não for especificado, o Hamiltonian deve ser interpretado como não dado na representação de buracos de partículas.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="5f6ed-203">Se presente, o valor da `particle_hole_representation` DEVE ser um objeto de quantidade escassa cujos índices são quatro inteiros, e cujos valores são um número e uma corda.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="5f6ed-204">A parte da cadeia do valor de cada elemento DEVE conter apenas os caracteres `'+'` e `'-'` que especifica se um determinado fator no termo é um operador de criação ou aniquilação na representação do buraco de partículas.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="5f6ed-205">Por exemplo, `"-+++"` responde a um buraco criado no local $i$ e partículas sendo criadas em locais $j, k$ e $l$.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="5f6ed-206">Dado que o valor da `particle_hole_representation` é um objeto de quantidade escassa de matriz, as propriedades `unit` e `format` devem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="5f6ed-207">As unidades aceitáveis incluem a lista do quadro 1.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="5f6ed-208">A propriedade `format` é necessária, e indica se os coeficientes hamiltonianos são especificados como uma matriz densa ou escassa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="5f6ed-209">Na versão atual, apenas são suportadas matrizes escassas, com a interpretação de que todos os elementos não especificados são $0$, mas futuras versões podem adicionar suporte para valores adicionais da propriedade `format`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="5f6ed-210">Secção inicial do Estado</span><span class="sxs-lookup"><span data-stu-id="5f6ed-210">Initial State Section</span></span> ###

<span data-ttu-id="5f6ed-211">O initial_state_suggestion objeto especifica os estados quânticos iniciais de interesse para o hamiltoniano especificado.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="5f6ed-212">Este objeto deve ser uma variedade de objetos `state` JSON.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="5f6ed-213">Objeto de Estado</span><span class="sxs-lookup"><span data-stu-id="5f6ed-213">State object</span></span> ####

<span data-ttu-id="5f6ed-214">Cada estado representa uma superposição de orbitais ocupados.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="5f6ed-215">Cada objeto de estado DEVE ter uma propriedade `label` contendo uma corda.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="5f6ed-216">Cada objeto de Estado DEVE ter uma propriedade `superposition` contendo uma série de estados de base e as suas amplitudes não normalizadas.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="5f6ed-217">Por exemplo, os estados iniciais $$ \ket {G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a{\dagger}\_2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}$$ $$ \ket{E}=\frac{{{\_{{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow}}}0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow}}{sqrt{0.1^2+/0,{0} 2 por</span><span class="sxs-lookup"><span data-stu-id="5f6ed-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="5f6ed-218">Objeto de conjunto de base</span><span class="sxs-lookup"><span data-stu-id="5f6ed-218">Basis Set Object</span></span> ####

<span data-ttu-id="5f6ed-219">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-219">This section is normative.</span></span>

<span data-ttu-id="5f6ed-220">Cada objeto conjunto integral PODE ter uma propriedade `basis_set`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="5f6ed-221">Se presente, o valor da propriedade `basis_set` DEVE ser um objeto com duas propriedades, `type` e `name`.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="5f6ed-222">As funções base identificadas pelo valor do `basis_set` imóvel DEVEM ser avaliadas em real.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="5f6ed-223">O pressuposto de que todas as funções base são de valor real pode ser relaxado em futuras versões desta especificação.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="5f6ed-224">Tabelas e Listas</span><span class="sxs-lookup"><span data-stu-id="5f6ed-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="5f6ed-225">Mesa 1.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-225">Table 1.</span></span> <span data-ttu-id="5f6ed-226">Unidades Físicas Permitidas</span><span class="sxs-lookup"><span data-stu-id="5f6ed-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="5f6ed-227">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-227">This section is normative.</span></span>

<span data-ttu-id="5f6ed-228">Qualquer cadeia que especifique uma unidade DEVE ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="5f6ed-229">Os parsers e os produtores devem tratar os seguintes objetos de quantidade simples como equivalentes:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="5f6ed-230">Mesa 2.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-230">Table 2.</span></span> <span data-ttu-id="5f6ed-231">Convenções de índice sinuosas</span><span class="sxs-lookup"><span data-stu-id="5f6ed-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="5f6ed-232">Esta secção é normativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-232">This section is normative.</span></span>

<span data-ttu-id="5f6ed-233">Qualquer cadeia que especifique uma convenção de índice deve ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="5f6ed-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="5f6ed-234">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-234">This section is informative.</span></span>

<span data-ttu-id="5f6ed-235">As convenções de índiceadicionais podem ser introduzidas em futuras versões desta especificação.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="5f6ed-236">Interpretação das Convenções de Índices</span><span class="sxs-lookup"><span data-stu-id="5f6ed-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="5f6ed-237">Esta secção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5f6ed-237">This section is informative.</span></span>
