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
# <a name="broombridge-specification-v01"></a>Especificação de Broombridge v 0,1 #

As palavras-chave "deve", "não deve", "REQUIRED", "is", "maio" e "OPTIONAL" neste documento devem ser interpretadas conforme descrito em [RFC 2119](https://tools.ietf.org/html/rfc2119)(recomendável), "pode" e "opcional" neste documentos.

Qualquer barra lateral com os títulos "observação", "informações" ou "aviso" é informativa.

## <a name="introduction"></a>Introdução ##

Esta seção é informativa.

Os documentos do Broombridge destinam-se a comunicar instâncias de problemas de simulação na química do Quantum para processamento usando simulação de Quantum e programação cadeias.

## <a name="serialization"></a>Série ##

Esta seção é normativas.

Um documento Broombridge deve ser serializado como um [documento YAML 1,2](http://yaml.org/spec/) que representa um objeto JSON, conforme descrito em [RFC 4627](https://tools.ietf.org/html/rfc4627) seção 2,2.
O objeto serializado para YAML deve ter uma propriedade `"$schema"` cujo valor é `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`e deve ser válido de acordo com as especificações de rascunho do esquema JSON-06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Para o restante desta especificação, "o objeto Broombridge" fará referência ao objeto JSON desserializado de um documento Broombridge YAML.

A menos que indicado de outra forma explicitamente, os objetos não devem ter propriedades adicionais além daquelas especificadas explicitamente neste documento.

## <a name="additional-definitions"></a>Definições Adicionais ##

Esta seção é normativas.

### <a name="quantity-objects"></a>Quantidade de objetos ###

Esta seção é normativas.

Um _objeto Quantity_ é um objeto JSON e deve ter uma propriedade `units` cujo valor é um dos valores permitidos listados na tabela 1.

Um objeto de quantidade é um _objeto de quantidade simples_ se tiver uma única propriedade `value` além de sua propriedade `units`.
O valor da propriedade `value` deve ser um número.

Um objeto Quantity é um _objeto de quantidade vinculada_ se tiver as propriedades `lower` e `upper` além de sua propriedade `units`.
Os valores das propriedades `lower` e `upper` devem ser números.
Um objeto de quantidade associada pode ter uma propriedade `value` cujo valor é um número.

Um objeto Quantity é um _objeto de quantidade de matriz esparsa_ se tiver a propriedade `format` e uma propriedade `values` além de sua propriedade `units`.
O valor de `format` deve ser a cadeia de caracteres `sparse`.
O valor da propriedade `values` deve ser uma matriz.
Cada elemento de `values` deve ser uma matriz que representa os índices e o valor da quantidade de matriz esparsa.

Os índices para cada elemento de um objeto de quantidade de matriz esparsa devem ser exclusivos em todo o objeto de quantidade de matriz esparsa.
Se um índice estiver presente com um valor de `0`, um analisador deverá tratar o objeto de quantidade de matriz esparsa de forma idêntica a um objeto de quantidade de matriz esparsa no qual esse índice não está presente.


Um objeto de quantidade deve ser

- um objeto de quantidade simples,
- um objeto de quantidade vinculada ou
- um objeto de quantidade de matriz esparsa.


### <a name="examples"></a>Exemplos ###

Esta seção é informativa.

Uma quantidade simples representando $1.9844146837\,\mathrm{Ha} $:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Uma quantidade limitada que representa uma distribuição uniforme sobre o intervalo $ [-7,-6]\,\mathrm{Ha} $:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

A seguir está uma quantidade de matriz esparsa com um elemento `[1, 2]` igual a `hello` e um elemento `[3, 4]` igual a `world`:

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Seção de formato ##

Esta seção é normativas.

O objeto Broombridge deve ter uma propriedade `format` cujo valor é um objeto JSON com uma propriedade chamada `version`.
A propriedade `version` deve ter o valor `"0.1"`.

### <a name="example"></a>Exemplo ###

Esta seção é informativa.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Seção de conjuntos integrais ##

Esta seção é normativas.

O objeto Broombridge deve ter uma propriedade `integral_sets` cujo valor é uma matriz JSON.
Cada item no valor da propriedade `integral_sets` deve ser um objeto JSON que descreve um conjunto de integrais, conforme descrito no restante desta seção.
No restante desta seção, o termo "objeto de conjunto integral" fará referência a um item no valor da propriedade `integral_sets` do objeto Broombridge.

Cada objeto de conjunto integral deve ter uma propriedade `metadata` cujo valor é um objeto JSON.
O valor de `metadata` pode ser o objeto JSON vazio (ou seja, `{}`) ou pode conter propriedades adicionais definidas pelo implementador.

### <a name="hamiltonian-section"></a>Seção Hamiltonian ###

#### <a name="overview"></a>Visão geral ####

Esta seção é informativa.

A propriedade `hamiltonian` de cada objeto de conjunto integral descreve o Hamiltonian para um problema de química do Quantum específico, listando seus termos de um e dois corpo como matrizes esparsas de números reais.
Os operadores Hamiltonian descritos por cada objeto de conjunto integral assumem o formulário

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

Aqui $h _ {ijkl} = (IJ | KL) $ na Convenção Mulliken.

Para maior clareza, o termo One-at é

$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

e o termo de duas-bits é

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).
$$

Conforme observado em nossa descrição da [propriedade`basis_set`](#basis-set-object) de cada elemento da propriedade `integral_sets`, declaromos mais explicitamente que as funções de base usadas são de valor real.
Isso nos permite usar os seguintes Symmetries entre os termos para compactar a representação do Hamiltonian.

$ $ h_ {ijkl} = h_ {Ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {LKJI}.
$$


#### <a name="contents"></a>Conteúdos ####

Esta seção é normativas.

Cada conjunto integral deve ter uma propriedade `hamiltonian` cujo valor é um objeto JSON.
O valor da propriedade `hamiltonian` é conhecido como um objeto Hamiltonian e deve ter as propriedades `one_electron_integrals` e `two_electron_integrals` conforme descrito no restante desta seção.
Um objeto Hamiltonian também pode ter uma propriedade `particle_hole_representation`.
Se estiver presente, o valor de `particle_hole_representation` deverá seguir o formato descrito no restante desta seção.

##### <a name="one-electron-integrals-object"></a>Objeto de integral de um único- #####

Esta seção é normativas.

A propriedade `one_electron_integrals` do objeto Hamiltonian deve ser uma quantidade de matriz esparsa cujos índices são dois inteiros e cujos valores são números.
Cada termo deve ter índices `[i, j]` onde `i >= j`.

> ANOTAÇÕES Isso reflete a simetria de que $h _ {IJ} = h_ {ji} $, que é uma conseqüência do fato de que o Hamiltonian é Hermitian.


###### <a name="example"></a>Exemplo ######

Esta seção é informativa.

A quantidade de matriz esparsa a seguir representa o Hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
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
> Broombridge usa indexação com base em 1.


##### <a name="two-electron-integrals-object"></a>Objeto de integral de dois bits #####

Esta seção é normativas.

A propriedade `two_electron_integrals` do objeto Hamiltonian deve ser uma quantidade de matriz esparsa com uma propriedade adicional chamada `index_convention`.
Cada elemento do valor de `two_electron_integrals` deve ter quatro índices.

Cada propriedade de `two_electron_integrals` deve ter uma propriedade `index_convention`.
O valor da propriedade `index_convention` deve ser um dos valores permitidos listados na tabela 1.
Se o valor de `index_convention` for `mulliken`, para cada elemento da quantidade de matriz esparsa de `two_electron_integrals`, um analisador que carrega um documento Broombridge deve criar uma instância de um termo Hamiltonian igual ao operador de dois bits $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k A_L $ , em que $i $, $j $, $k $ e $l $ devem ser inteiros no intervalo inclusivo de 1 até o número de elétrons especificado pela propriedade `n_electrons` do objeto de conjunto integral e em que $h _ {i, j, k, l} $ é o elemento `[i, j, k, l, h(i, j, k, l)]` da quantidade de matriz esparsa.

###### <a name="symmetries"></a>Symmetries ######

Esta seção é normativas.

Se a propriedade `index_convention` de um objeto `two_electron_integrals` for igual a `mulliken`, se um elemento com índices `[i, j, k, l]` estiver presente, os índices a seguir não deverão estar presentes, a menos que sejam iguais a `[i, j, k, l]`:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Como a propriedade `index_convention` é um objeto de quantidade esparsa, nenhum índice pode ser repetido em elementos diferentes.
> Em particular, se um elemento com índices `[i, j, k, l]` estiver presente, nenhum outro elemento poderá ter esses índices.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Exemplo #######

Esta seção é informativa.

O objeto a seguir especifica o Hamiltonian

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 , \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
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

##### <a name="particlehole-representation-object"></a>Partícula – objeto de representação de orifício #####

Esta seção é normativas.

O objeto partícula – representação de orifício especifica que os integrais armazenados são definidos com relação à representação de orifícios de partículas, em que os operadores de criação e Annihilation descrevem excitations fora do estado de referência usado, como um Hartree – Estado de Fock.
O objeto é opcional.
Se o objeto não for especificado, o Hamiltonian será interpretado como não fornecido na representação de orifício de partículas.
Se presente, o valor de `particle_hole_representation` deve ser um objeto de quantidade de matriz esparsa cujos índices são quatro inteiros e cujos valores são um número e uma cadeia de caracteres.
A parte da cadeia de caracteres do valor de cada elemento deve conter somente os caracteres `'+'` e `'-'` que especifica se um determinado fator no termo é um operador de criação ou Annihilation na partícula – representação de buraco.  Por exemplo `"-+++"` coresponder a um orifício que está sendo criado no site $i $ e as partículas que estão sendo criadas nos sites $j, k $ e $l $.

> [!NOTE]
> Como o valor da `particle_hole_representation` é um objeto de quantidade de matriz esparsa, as propriedades `unit` e `format` devem ser especificadas.
> As unidades aceitáveis incluem listadas na tabela 1.
> A propriedade `format` é necessária e indica se os coeficientes Hamiltonian são especificados como uma matriz densa ou esparsa.
> Na versão atual, somente as matrizes esparsas têm suporte, com a interpretação de que todos os elementos não especificados são $0 $, mas as versões futuras podem adicionar suporte para valores adicionais da propriedade `format`.

### <a name="initial-state-section"></a>Seção de estado inicial ###

O objeto initial_state_suggestion especifica os Estados de Quantum inicial de interesse para o Hamiltonian especificado. Esse objeto deve ser uma matriz de objetos `state` JSON.

#### <a name="state-object"></a>Objeto de estado ####

Cada Estado representa uma superposição de órbitas ocupados. Cada objeto de Estado deve ter uma propriedade `label` contendo uma cadeia de caracteres. Cada objeto de Estado deve ter uma propriedade `superposition` contendo uma matriz de Estados de base e suas amplitudes não normalizadas.

Por exemplo, os Estados iniciais $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0.2 | ^ 2}} \ket{0} $ $ são representado por
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

#### <a name="basis-set-object"></a>Objeto de conjunto base ####

Esta seção é normativas.

Cada objeto de conjunto integral pode ter uma propriedade `basis_set`.
Se houver, o valor da propriedade `basis_set` deve ser um objeto com duas propriedades, `type` e `name`.

As funções base identificadas pelo valor da propriedade `basis_set` devem ser de valor real.

> [!NOTE]
> A suposição de que todas as funções de base tenham valor real pode ser reduzida em versões futuras desta especificação.

## <a name="tables-and-lists"></a>Tabelas e listas ##

### <a name="table-1-allowed-physical-units"></a>Tabela 1. Unidades físicas permitidas ###

Esta seção é normativas.

Qualquer cadeia de caracteres especificando uma unidade deve ser uma das seguintes:

- `hartree`
- `ev`

Analisadores e produtores devem tratar os seguintes objetos de quantidade simples como equivalentes:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabela 2. Convenções de índice permitidas ###

Esta seção é normativas.

Qualquer cadeia de caracteres especificando uma Convenção de índice deve ser uma das seguintes:

- `mulliken`

Esta seção é informativa.

As convenções de índice adicionais podem ser introduzidas em versões futuras desta especificação.

#### <a name="interpretation-of-index-conventions"></a>Interpretação de convenções de índice ####

Esta seção é informativa.
