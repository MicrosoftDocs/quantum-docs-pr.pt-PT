---
title: Especificação de esquema Broombridge
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: 2f4be96bc6f1e8e6fe21b93bc0d9ab2aa367fd53
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185312"
---
# <a name="broombridge-specification-v02"></a>Especificação Broombridge v 0.2 #

As palavras-chave "deve", "não deve", "REQUIRED", "is", "maio" e "OPTIONAL" neste documento devem ser interpretadas conforme descrito em [RFC 2119](https://tools.ietf.org/html/rfc2119)(recomendável), "pode" e "opcional" neste documentos.

Qualquer barra lateral com os títulos "observação", "informações" ou "aviso" é informativa.

## <a name="introduction"></a>Introdução ##

Esta seção é informativa.

Os documentos do Broombridge destinam-se a comunicar instâncias de problemas de simulação na química do Quantum para processamento usando simulação de Quantum e programação cadeias.

## <a name="serialization"></a>Série ##

Esta seção é normativas.

Um documento Broombridge deve ser serializado como um [documento YAML 1,2](http://yaml.org/spec/) que representa um objeto JSON, conforme descrito em [RFC 4627](https://tools.ietf.org/html/rfc4627) seção 2,2.
O objeto serializado para YAML deve ter uma propriedade `"$schema"` cujo valor é `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`e deve ser válido de acordo com as especificações de rascunho do esquema JSON-06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

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
A propriedade `version` deve ter o valor `"0.2"`.

### <a name="example"></a>Exemplo ###

Esta seção é informativa.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Seção Descrição do problema ##

Esta seção é normativas.

O objeto Broombridge deve ter uma propriedade `problem_description` cujo valor é uma matriz JSON.
Cada item no valor da propriedade `problem_description` deve ser um objeto JSON que descreve um conjunto de integrais, conforme descrito no restante desta seção.
No restante desta seção, o termo "objeto de descrição do problema" fará referência a um item no valor da propriedade `problem_description` do objeto Broombridge.

Cada objeto de descrição do problema deve ter uma propriedade `metadata` cujo valor é um objeto JSON.
O valor de `metadata` pode ser o objeto JSON vazio (ou seja, `{}`) ou pode conter propriedades adicionais definidas pelo implementador.

### <a name="hamiltonian-section"></a>Seção Hamiltonian ###

#### <a name="overview"></a>Visão geral ####

Esta seção é informativa.

A propriedade `hamiltonian` de cada objeto de descrição do problema descreve o Hamiltonian para um problema de química do Quantum específico, listando seus termos de um e dois corpo como matrizes esparsas de números reais.
Os operadores de Hamiltonian descritos por cada objeto de descrição de problema assumem o formulário

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

Cada objeto de descrição do problema deve ter uma propriedade `hamiltonian` cujo valor é um objeto JSON.
O valor da propriedade `hamiltonian` é conhecido como um objeto Hamiltonian e deve ter as propriedades `one_electron_integrals` e `two_electron_integrals` conforme descrito no restante desta seção.

Cada objeto de descrição do problema deve ter uma propriedade `coulomb_repulsion` cujo valor é um objeto de quantidade simples.
Cada objeto de descrição do problema deve ter uma propriedade `energy_offet` cujo valor é um objeto de quantidade simples.
> ANOTAÇÕES Os valores de `coulomb_repulsion` e `energy_offet` adicionados juntos capturam o termo de identidade do Hamiltonian.

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
Se o valor de `index_convention` for `mulliken`, para cada elemento da quantidade de matriz esparsa de `two_electron_integrals`, um analisador que carrega um documento Broombridge deve criar uma instância de um termo Hamiltonian igual ao operador de dois bits $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k A_L $ , em que $i $, $j $, $k $ e $l $ devem ser inteiros de valor pelo menos 1 e em que $h _ {i, j, k, l} $ é o elemento `[i, j, k, l, h(i, j, k, l)]` da quantidade de matriz esparsa.

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

### <a name="initial-state-section"></a>Seção de estado inicial ###

Esta seção é normativas.

O objeto `initial_state_suggestion` cujo valor é uma matriz JSON especifica os Estados de Quantum inicial de interesse para o Hamiltonian especificado. Cada item no valor da propriedade `initial_state_suggestion` deve ser um objeto JSON que descreve um estado Quantum, conforme descrito no restante desta seção.
No restante desta seção, o termo "objeto de estado" fará referência a um item no valor da propriedade `initial_state_suggestion` do objeto Broombridge.

#### <a name="state-object"></a>Objeto de estado ####

Esta seção é normativas.

Cada objeto de Estado deve ter uma propriedade `label` contendo uma cadeia de caracteres. Cada objeto de Estado deve ter uma propriedade `method`. O valor da propriedade `method` deve ser um dos valores permitidos listados na tabela 3.
Cada objeto de estado pode ter uma propriedade `energy` cujo valor deve ser um objeto de quantidade simples.

Se o valor da propriedade `method` for `sparse_multi_configurational`, o objeto de estado deverá ter uma propriedade `superposition` que contenha uma matriz de Estados de base e suas amplitudes não normalizadas.

Por exemplo, os Estados iniciais $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0.2 | ^ 2}} \ket{0}, $ $, em que $ \ket{E} $ tem Energy $0.987 \textrm{Ha} $, são representados por
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

Se o valor da propriedade `method` for `unitary_coupled_cluster`, o objeto de estado deverá ter uma propriedade `cluster_operator` cujo valor é um objeto JSON.
O objeto JSON deve ter uma propriedade `reference_state` cujo valor é um estado base.
O objeto JSON pode ter uma propriedade `one_body_amplitudes` cujo valor é uma matriz de operadores de cluster de um corpo e suas amplitudes.
O objeto JSON pode ter uma propriedade `two_body_amplitudes` cujo valor é uma matriz de operadores de cluster de dois corpo e suas amplitudes.
que contém uma matriz de Estados de base e suas amplitudes não normalizadas.

Por exemplo, o estado $ $ \ket{\Text{Reference}} = (um ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0}, $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{Reference}}, $ $

$ $ T = 0,1 a ^ {\dagger}\_{3, \uparrow}a\_{2, \downarrow} + 0,2 a ^ {\dagger}\_{2, \uparrow}a\_{2, \downarrow}-0,3 a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \downarrow}a\_{3 , \uparrow}a\_{2, \downarrow} $ $ é representado por
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

#### <a name="basis-set-object"></a>Objeto de conjunto base ####

Esta seção é normativas.

Cada objeto de descrição do problema pode ter uma propriedade `basis_set`.
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

### <a name="table-3-allowed-state-methods"></a>Tabela 3. Métodos de estado permitidos ###

Esta seção é normativas.

Qualquer cadeia de caracteres especificando um método de Estado deve ser uma das seguintes:

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Esta seção é informativa.

Métodos de estado adicionais podem ser introduzidos em versões futuras desta especificação.
