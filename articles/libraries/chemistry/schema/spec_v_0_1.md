---
title: Especificação de esquema Broombridge
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185363"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="5242c-102">Especificação de Broombridge v 0,1</span><span class="sxs-lookup"><span data-stu-id="5242c-102">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="5242c-103">As palavras-chave "deve", "não deve", "REQUIRED", "is", "maio" e "OPTIONAL" neste documento devem ser interpretadas conforme descrito em [RFC 2119](https://tools.ietf.org/html/rfc2119)(recomendável), "pode" e "opcional" neste documentos.</span><span class="sxs-lookup"><span data-stu-id="5242c-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="5242c-104">Qualquer barra lateral com os títulos "observação", "informações" ou "aviso" é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="5242c-105">Introdução</span><span class="sxs-lookup"><span data-stu-id="5242c-105">Introduction</span></span> ##

<span data-ttu-id="5242c-106">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-106">This section is informative.</span></span>

<span data-ttu-id="5242c-107">Os documentos do Broombridge destinam-se a comunicar instâncias de problemas de simulação na química do Quantum para processamento usando simulação de Quantum e programação cadeias.</span><span class="sxs-lookup"><span data-stu-id="5242c-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="5242c-108">Série</span><span class="sxs-lookup"><span data-stu-id="5242c-108">Serialization</span></span> ##

<span data-ttu-id="5242c-109">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-109">This section is normative.</span></span>

<span data-ttu-id="5242c-110">Um documento Broombridge deve ser serializado como um [documento YAML 1,2](http://yaml.org/spec/) que representa um objeto JSON, conforme descrito em [RFC 4627](https://tools.ietf.org/html/rfc4627) seção 2,2.</span><span class="sxs-lookup"><span data-stu-id="5242c-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="5242c-111">O objeto serializado para YAML deve ter uma propriedade `"$schema"` cujo valor é `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`e deve ser válido de acordo com as especificações de rascunho do esquema JSON-06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="5242c-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="5242c-112">Para o restante desta especificação, "o objeto Broombridge" fará referência ao objeto JSON desserializado de um documento Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="5242c-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="5242c-113">A menos que indicado de outra forma explicitamente, os objetos não devem ter propriedades adicionais além daquelas especificadas explicitamente neste documento.</span><span class="sxs-lookup"><span data-stu-id="5242c-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="5242c-114">Definições Adicionais</span><span class="sxs-lookup"><span data-stu-id="5242c-114">Additional Definitions</span></span> ##

<span data-ttu-id="5242c-115">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="5242c-116">Quantidade de objetos</span><span class="sxs-lookup"><span data-stu-id="5242c-116">Quantity Objects</span></span> ###

<span data-ttu-id="5242c-117">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-117">This section is normative.</span></span>

<span data-ttu-id="5242c-118">Um _objeto Quantity_ é um objeto JSON e deve ter uma propriedade `units` cujo valor é um dos valores permitidos listados na tabela 1.</span><span class="sxs-lookup"><span data-stu-id="5242c-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="5242c-119">Um objeto de quantidade é um _objeto de quantidade simples_ se tiver uma única propriedade `value` além de sua propriedade `units`.</span><span class="sxs-lookup"><span data-stu-id="5242c-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="5242c-120">O valor da propriedade `value` deve ser um número.</span><span class="sxs-lookup"><span data-stu-id="5242c-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="5242c-121">Um objeto Quantity é um _objeto de quantidade vinculada_ se tiver as propriedades `lower` e `upper` além de sua propriedade `units`.</span><span class="sxs-lookup"><span data-stu-id="5242c-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="5242c-122">Os valores das propriedades `lower` e `upper` devem ser números.</span><span class="sxs-lookup"><span data-stu-id="5242c-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="5242c-123">Um objeto de quantidade associada pode ter uma propriedade `value` cujo valor é um número.</span><span class="sxs-lookup"><span data-stu-id="5242c-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="5242c-124">Um objeto Quantity é um _objeto de quantidade de matriz esparsa_ se tiver a propriedade `format` e uma propriedade `values` além de sua propriedade `units`.</span><span class="sxs-lookup"><span data-stu-id="5242c-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="5242c-125">O valor de `format` deve ser a cadeia de caracteres `sparse`.</span><span class="sxs-lookup"><span data-stu-id="5242c-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="5242c-126">O valor da propriedade `values` deve ser uma matriz.</span><span class="sxs-lookup"><span data-stu-id="5242c-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="5242c-127">Cada elemento de `values` deve ser uma matriz que representa os índices e o valor da quantidade de matriz esparsa.</span><span class="sxs-lookup"><span data-stu-id="5242c-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="5242c-128">Os índices para cada elemento de um objeto de quantidade de matriz esparsa devem ser exclusivos em todo o objeto de quantidade de matriz esparsa.</span><span class="sxs-lookup"><span data-stu-id="5242c-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="5242c-129">Se um índice estiver presente com um valor de `0`, um analisador deverá tratar o objeto de quantidade de matriz esparsa de forma idêntica a um objeto de quantidade de matriz esparsa no qual esse índice não está presente.</span><span class="sxs-lookup"><span data-stu-id="5242c-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="5242c-130">Um objeto de quantidade deve ser</span><span class="sxs-lookup"><span data-stu-id="5242c-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="5242c-131">um objeto de quantidade simples,</span><span class="sxs-lookup"><span data-stu-id="5242c-131">a simple quantity object,</span></span>
- <span data-ttu-id="5242c-132">um objeto de quantidade vinculada ou</span><span class="sxs-lookup"><span data-stu-id="5242c-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="5242c-133">um objeto de quantidade de matriz esparsa.</span><span class="sxs-lookup"><span data-stu-id="5242c-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="5242c-134">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5242c-134">Examples</span></span> ###

<span data-ttu-id="5242c-135">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-135">This section is informative.</span></span>

<span data-ttu-id="5242c-136">Uma quantidade simples representando $1.9844146837\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="5242c-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="5242c-137">Uma quantidade limitada que representa uma distribuição uniforme sobre o intervalo $ [-7,-6]\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="5242c-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="5242c-138">A seguir está uma quantidade de matriz esparsa com um elemento `[1, 2]` igual a `hello` e um elemento `[3, 4]` igual a `world`:</span><span class="sxs-lookup"><span data-stu-id="5242c-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="5242c-139">Seção de formato</span><span class="sxs-lookup"><span data-stu-id="5242c-139">Format Section</span></span> ##

<span data-ttu-id="5242c-140">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-140">This section is normative.</span></span>

<span data-ttu-id="5242c-141">O objeto Broombridge deve ter uma propriedade `format` cujo valor é um objeto JSON com uma propriedade chamada `version`.</span><span class="sxs-lookup"><span data-stu-id="5242c-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="5242c-142">A propriedade `version` deve ter o valor `"0.1"`.</span><span class="sxs-lookup"><span data-stu-id="5242c-142">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="5242c-143">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5242c-143">Example</span></span> ###

<span data-ttu-id="5242c-144">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="5242c-145">Seção de conjuntos integrais</span><span class="sxs-lookup"><span data-stu-id="5242c-145">Integral Sets Section</span></span> ##

<span data-ttu-id="5242c-146">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-146">This section is normative.</span></span>

<span data-ttu-id="5242c-147">O objeto Broombridge deve ter uma propriedade `integral_sets` cujo valor é uma matriz JSON.</span><span class="sxs-lookup"><span data-stu-id="5242c-147">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="5242c-148">Cada item no valor da propriedade `integral_sets` deve ser um objeto JSON que descreve um conjunto de integrais, conforme descrito no restante desta seção.</span><span class="sxs-lookup"><span data-stu-id="5242c-148">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="5242c-149">No restante desta seção, o termo "objeto de conjunto integral" fará referência a um item no valor da propriedade `integral_sets` do objeto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="5242c-149">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="5242c-150">Cada objeto de conjunto integral deve ter uma propriedade `metadata` cujo valor é um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="5242c-150">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="5242c-151">O valor de `metadata` pode ser o objeto JSON vazio (ou seja, `{}`) ou pode conter propriedades adicionais definidas pelo implementador.</span><span class="sxs-lookup"><span data-stu-id="5242c-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="5242c-152">Seção Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="5242c-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="5242c-153">Visão geral</span><span class="sxs-lookup"><span data-stu-id="5242c-153">Overview</span></span> ####

<span data-ttu-id="5242c-154">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-154">This section is informative.</span></span>

<span data-ttu-id="5242c-155">A propriedade `hamiltonian` de cada objeto de conjunto integral descreve o Hamiltonian para um problema de química do Quantum específico, listando seus termos de um e dois corpo como matrizes esparsas de números reais.</span><span class="sxs-lookup"><span data-stu-id="5242c-155">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="5242c-156">Os operadores Hamiltonian descritos por cada objeto de conjunto integral assumem o formulário</span><span class="sxs-lookup"><span data-stu-id="5242c-156">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="5242c-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="5242c-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="5242c-158">Aqui $h _ {ijkl} = (IJ | KL) $ na Convenção Mulliken.</span><span class="sxs-lookup"><span data-stu-id="5242c-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="5242c-159">Para maior clareza, o termo One-at é</span><span class="sxs-lookup"><span data-stu-id="5242c-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="5242c-160">$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="5242c-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="5242c-161">e o termo de duas-bits é</span><span class="sxs-lookup"><span data-stu-id="5242c-161">and the two-electron term is</span></span>

<span data-ttu-id="5242c-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="5242c-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="5242c-163">Conforme observado em nossa descrição da [propriedade`basis_set`](#basis-set-object) de cada elemento da propriedade `integral_sets`, declaromos mais explicitamente que as funções de base usadas são de valor real.</span><span class="sxs-lookup"><span data-stu-id="5242c-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="5242c-164">Isso nos permite usar os seguintes Symmetries entre os termos para compactar a representação do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5242c-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="5242c-165">$ $ h_ {ijkl} = h_ {Ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {LKJI}.</span><span class="sxs-lookup"><span data-stu-id="5242c-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="5242c-166">Conteúdos</span><span class="sxs-lookup"><span data-stu-id="5242c-166">Contents</span></span> ####

<span data-ttu-id="5242c-167">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-167">This section is normative.</span></span>

<span data-ttu-id="5242c-168">Cada conjunto integral deve ter uma propriedade `hamiltonian` cujo valor é um objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="5242c-168">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="5242c-169">O valor da propriedade `hamiltonian` é conhecido como um objeto Hamiltonian e deve ter as propriedades `one_electron_integrals` e `two_electron_integrals` conforme descrito no restante desta seção.</span><span class="sxs-lookup"><span data-stu-id="5242c-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="5242c-170">Um objeto Hamiltonian também pode ter uma propriedade `particle_hole_representation`.</span><span class="sxs-lookup"><span data-stu-id="5242c-170">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="5242c-171">Se estiver presente, o valor de `particle_hole_representation` deverá seguir o formato descrito no restante desta seção.</span><span class="sxs-lookup"><span data-stu-id="5242c-171">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="5242c-172">Objeto de integral de um único-</span><span class="sxs-lookup"><span data-stu-id="5242c-172">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="5242c-173">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-173">This section is normative.</span></span>

<span data-ttu-id="5242c-174">A propriedade `one_electron_integrals` do objeto Hamiltonian deve ser uma quantidade de matriz esparsa cujos índices são dois inteiros e cujos valores são números.</span><span class="sxs-lookup"><span data-stu-id="5242c-174">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="5242c-175">Cada termo deve ter índices `[i, j]` onde `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="5242c-175">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="5242c-176">ANOTAÇÕES Isso reflete a simetria de que $h _ {IJ} = h_ {ji} $, que é uma conseqüência do fato de que o Hamiltonian é Hermitian.</span><span class="sxs-lookup"><span data-stu-id="5242c-176">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="5242c-177">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5242c-177">Example</span></span> ######

<span data-ttu-id="5242c-178">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-178">This section is informative.</span></span>

<span data-ttu-id="5242c-179">A quantidade de matriz esparsa a seguir representa o Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="5242c-179">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="5242c-180">Broombridge usa indexação com base em 1.</span><span class="sxs-lookup"><span data-stu-id="5242c-180">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="5242c-181">Objeto de integral de dois bits</span><span class="sxs-lookup"><span data-stu-id="5242c-181">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="5242c-182">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-182">This section is normative.</span></span>

<span data-ttu-id="5242c-183">A propriedade `two_electron_integrals` do objeto Hamiltonian deve ser uma quantidade de matriz esparsa com uma propriedade adicional chamada `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="5242c-183">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="5242c-184">Cada elemento do valor de `two_electron_integrals` deve ter quatro índices.</span><span class="sxs-lookup"><span data-stu-id="5242c-184">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="5242c-185">Cada propriedade de `two_electron_integrals` deve ter uma propriedade `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="5242c-185">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="5242c-186">O valor da propriedade `index_convention` deve ser um dos valores permitidos listados na tabela 1.</span><span class="sxs-lookup"><span data-stu-id="5242c-186">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="5242c-187">Se o valor de `index_convention` for `mulliken`, para cada elemento da quantidade de matriz esparsa de `two_electron_integrals`, um analisador que carrega um documento Broombridge deve criar uma instância de um termo Hamiltonian igual ao operador de dois bits $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k A_L $ , em que $i $, $j $, $k $ e $l $ devem ser inteiros no intervalo inclusivo de 1 até o número de elétrons especificado pela propriedade `n_electrons` do objeto de conjunto integral e em que $h _ {i, j, k, l} $ é o elemento `[i, j, k, l, h(i, j, k, l)]` da quantidade de matriz esparsa.</span><span class="sxs-lookup"><span data-stu-id="5242c-187">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="5242c-188">Symmetries</span><span class="sxs-lookup"><span data-stu-id="5242c-188">Symmetries</span></span> ######

<span data-ttu-id="5242c-189">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-189">This section is normative.</span></span>

<span data-ttu-id="5242c-190">Se a propriedade `index_convention` de um objeto `two_electron_integrals` for igual a `mulliken`, se um elemento com índices `[i, j, k, l]` estiver presente, os índices a seguir não deverão estar presentes, a menos que sejam iguais a `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="5242c-190">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="5242c-191">Como a propriedade `index_convention` é um objeto de quantidade esparsa, nenhum índice pode ser repetido em elementos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5242c-191">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="5242c-192">Em particular, se um elemento com índices `[i, j, k, l]` estiver presente, nenhum outro elemento poderá ter esses índices.</span><span class="sxs-lookup"><span data-stu-id="5242c-192">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="5242c-193">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5242c-193">Example</span></span> #######

<span data-ttu-id="5242c-194">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-194">This section is informative.</span></span>

<span data-ttu-id="5242c-195">O objeto a seguir especifica o Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="5242c-195">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="5242c-196">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 , \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="5242c-196">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="5242c-197">Partícula – objeto de representação de orifício</span><span class="sxs-lookup"><span data-stu-id="5242c-197">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="5242c-198">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-198">This section is normative.</span></span>

<span data-ttu-id="5242c-199">O objeto partícula – representação de orifício especifica que os integrais armazenados são definidos com relação à representação de orifícios de partículas, em que os operadores de criação e Annihilation descrevem excitations fora do estado de referência usado, como um Hartree – Estado de Fock.</span><span class="sxs-lookup"><span data-stu-id="5242c-199">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="5242c-200">O objeto é opcional.</span><span class="sxs-lookup"><span data-stu-id="5242c-200">The object is OPTIONAL.</span></span>
<span data-ttu-id="5242c-201">Se o objeto não for especificado, o Hamiltonian será interpretado como não fornecido na representação de orifício de partículas.</span><span class="sxs-lookup"><span data-stu-id="5242c-201">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="5242c-202">Se presente, o valor de `particle_hole_representation` deve ser um objeto de quantidade de matriz esparsa cujos índices são quatro inteiros e cujos valores são um número e uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5242c-202">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="5242c-203">A parte da cadeia de caracteres do valor de cada elemento deve conter somente os caracteres `'+'` e `'-'` que especifica se um determinado fator no termo é um operador de criação ou Annihilation na partícula – representação de buraco.</span><span class="sxs-lookup"><span data-stu-id="5242c-203">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="5242c-204">Por exemplo `"-+++"` coresponder a um orifício que está sendo criado no site $i $ e as partículas que estão sendo criadas nos sites $j, k $ e $l $.</span><span class="sxs-lookup"><span data-stu-id="5242c-204">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="5242c-205">Como o valor da `particle_hole_representation` é um objeto de quantidade de matriz esparsa, as propriedades `unit` e `format` devem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="5242c-205">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="5242c-206">As unidades aceitáveis incluem listadas na tabela 1.</span><span class="sxs-lookup"><span data-stu-id="5242c-206">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="5242c-207">A propriedade `format` é necessária e indica se os coeficientes Hamiltonian são especificados como uma matriz densa ou esparsa.</span><span class="sxs-lookup"><span data-stu-id="5242c-207">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="5242c-208">Na versão atual, somente as matrizes esparsas têm suporte, com a interpretação de que todos os elementos não especificados são $0 $, mas as versões futuras podem adicionar suporte para valores adicionais da propriedade `format`.</span><span class="sxs-lookup"><span data-stu-id="5242c-208">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="5242c-209">Seção de estado inicial</span><span class="sxs-lookup"><span data-stu-id="5242c-209">Initial State Section</span></span> ###

<span data-ttu-id="5242c-210">O objeto initial_state_suggestion especifica os Estados de Quantum inicial de interesse para o Hamiltonian especificado.</span><span class="sxs-lookup"><span data-stu-id="5242c-210">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="5242c-211">Esse objeto deve ser uma matriz de objetos `state` JSON.</span><span class="sxs-lookup"><span data-stu-id="5242c-211">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="5242c-212">Objeto de estado</span><span class="sxs-lookup"><span data-stu-id="5242c-212">State object</span></span> ####

<span data-ttu-id="5242c-213">Cada Estado representa uma superposição de órbitas ocupados.</span><span class="sxs-lookup"><span data-stu-id="5242c-213">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="5242c-214">Cada objeto de Estado deve ter uma propriedade `label` contendo uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5242c-214">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="5242c-215">Cada objeto de Estado deve ter uma propriedade `superposition` contendo uma matriz de Estados de base e suas amplitudes não normalizadas.</span><span class="sxs-lookup"><span data-stu-id="5242c-215">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="5242c-216">Por exemplo, os Estados iniciais $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0.2 | ^ 2}} \ket{0} $ $ são representado por</span><span class="sxs-lookup"><span data-stu-id="5242c-216">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="5242c-217">Objeto de conjunto base</span><span class="sxs-lookup"><span data-stu-id="5242c-217">Basis Set Object</span></span> ####

<span data-ttu-id="5242c-218">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-218">This section is normative.</span></span>

<span data-ttu-id="5242c-219">Cada objeto de conjunto integral pode ter uma propriedade `basis_set`.</span><span class="sxs-lookup"><span data-stu-id="5242c-219">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="5242c-220">Se houver, o valor da propriedade `basis_set` deve ser um objeto com duas propriedades, `type` e `name`.</span><span class="sxs-lookup"><span data-stu-id="5242c-220">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="5242c-221">As funções base identificadas pelo valor da propriedade `basis_set` devem ser de valor real.</span><span class="sxs-lookup"><span data-stu-id="5242c-221">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="5242c-222">A suposição de que todas as funções de base tenham valor real pode ser reduzida em versões futuras desta especificação.</span><span class="sxs-lookup"><span data-stu-id="5242c-222">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="5242c-223">Tabelas e listas</span><span class="sxs-lookup"><span data-stu-id="5242c-223">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="5242c-224">Tabela 1.</span><span class="sxs-lookup"><span data-stu-id="5242c-224">Table 1.</span></span> <span data-ttu-id="5242c-225">Unidades físicas permitidas</span><span class="sxs-lookup"><span data-stu-id="5242c-225">Allowed Physical Units</span></span> ###

<span data-ttu-id="5242c-226">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-226">This section is normative.</span></span>

<span data-ttu-id="5242c-227">Qualquer cadeia de caracteres especificando uma unidade deve ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="5242c-227">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="5242c-228">Analisadores e produtores devem tratar os seguintes objetos de quantidade simples como equivalentes:</span><span class="sxs-lookup"><span data-stu-id="5242c-228">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="5242c-229">Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="5242c-229">Table 2.</span></span> <span data-ttu-id="5242c-230">Convenções de índice permitidas</span><span class="sxs-lookup"><span data-stu-id="5242c-230">Allowed Index Conventions</span></span> ###

<span data-ttu-id="5242c-231">Esta seção é normativas.</span><span class="sxs-lookup"><span data-stu-id="5242c-231">This section is normative.</span></span>

<span data-ttu-id="5242c-232">Qualquer cadeia de caracteres especificando uma Convenção de índice deve ser uma das seguintes:</span><span class="sxs-lookup"><span data-stu-id="5242c-232">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="5242c-233">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-233">This section is informative.</span></span>

<span data-ttu-id="5242c-234">As convenções de índice adicionais podem ser introduzidas em versões futuras desta especificação.</span><span class="sxs-lookup"><span data-stu-id="5242c-234">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="5242c-235">Interpretação de convenções de índice</span><span class="sxs-lookup"><span data-stu-id="5242c-235">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="5242c-236">Esta seção é informativa.</span><span class="sxs-lookup"><span data-stu-id="5242c-236">This section is informative.</span></span>
