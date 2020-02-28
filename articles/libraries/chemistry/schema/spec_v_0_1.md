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
# <a name="broombridge-specification-v01"></a>Especificação broombridge v0.1 #

As palavras-chave "MUST", "MUST NOT", "REQUIRED", "DEVE", "NÃO DEVE", "NÃO DEVEM", "RECOMENDADO", "MAIO" e "OPCIONAL" neste documento devem ser interpretadas como descrito no [RFC 2119.](https://tools.ietf.org/html/rfc2119)

Qualquer barra lateral com as rubricas "NOTA", "INFORMAÇÃO" ou "AVISO" é informativa.

## <a name="introduction"></a>Introdução ##

Esta secção é informativa.

Os documentos de Broombridge destinam-se a comunicar casos de problemas de simulação na química quântica para processamento utilizando cadeias de ferramentas de simulação quântica e programação.

## <a name="serialization"></a>Serialização ##

Esta secção é normativa.

Um documento broombridge DEVE ser serializado como um [documento YAML 1.2](http://yaml.org/spec/) que representa um objeto JSON, conforme descrito na secção 2.2 do [RFC 4627.](https://tools.ietf.org/html/rfc4627)
O objeto serializado para o YAML MUST tem uma propriedade `"$schema"` cujo valor seja `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, e DEVE ser válido de acordo com as especificações json schema[[1,](https://tools.ietf.org/html/draft-wright-json-schema-01) [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Para o resto desta especificação, "o objeto Broombridge" refere-se ao objeto JSON desserializado a partir de um documento YAML de Broombridge.

Salvo indicação em contrário, os objetos NÃO DEVEM ter propriedades adicionais para além das especificadas explicitamente neste documento.

## <a name="additional-definitions"></a>Definições adicionais ##

Esta secção é normativa.

### <a name="quantity-objects"></a>Objetos de quantidade ###

Esta secção é normativa.

Um _objeto de quantidade_ é um objeto JSON, e MUST tem um `units` de propriedade cujo valor é um dos valores permitidos listados no Quadro 1.

Um objeto de quantidade é um _objeto de quantidade simples_ se tiver uma única propriedade `value` além da sua propriedade `units`.
O valor da propriedade `value` DEVE ser um número.

Um objeto de quantidade é um objeto de _quantidade limitado_ se tiver as propriedades `lower` e `upper` além da sua propriedade `units`.
Os valores das propriedades `lower` e `upper` devem ser números.
Um objeto de quantidade limitado PODE ter uma propriedade `value` cujo valor é um número.

Um objeto de quantidade é um _objeto de quantidade escassa_ se tiver a propriedade `format` e uma propriedade `values` além da sua propriedade `units`.
O valor do `format` DEVE ser a cadeia `sparse`.
O valor da propriedade `values` DEVE ser uma matriz.
Cada elemento de `values` DEVE ser um matriz que representa os índices e o valor da escassa quantidade de matriz.

Os índices para cada elemento de um objeto de quantidade escassa de matriz DEVEM ser únicos em todo o objeto de quantidade de matriz escassa.
Se um índice estiver presente com um valor de `0`, um parser MUST tratar o objeto de quantidade escassa de matriz de forma idêntica a um objeto de quantidade escassa de matriz em que esse índice não esteja presente.


Um objeto de quantidade DEVE ser

- um simples objeto de quantidade,
- um objeto de quantidade limitado, ou
- um objeto de quantidade escassa de matriz.


### <a name="examples"></a>Exemplos ###

Esta secção é informativa.

Uma quantidade simples que representa $1.9844146837\,\mathrm{Ha}$:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Uma quantidade limitada que representa uma distribuição uniforme ao longo do intervalo $[-7, -6]\,\mathrm{Ha}$:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Segue-se uma quantidade escassa de matriz com um elemento `[1, 2]` igual a `hello` e um elemento `[3, 4]` igual a `world`:

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Secção de Formato ##

Esta secção é normativa.

O objeto broombridge MUST tem uma propriedade `format` cujo valor é um objeto JSON com uma propriedade chamada `version`.
A propriedade `version` DEVE ter o valor `"0.1"`.

### <a name="example"></a>Exemplo ###

Esta secção é informativa.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Secção conjuntos integrais ##

Esta secção é normativa.

O objeto broombridge MUST tem uma propriedade `integral_sets` cujo valor é uma matriz JSON.
Cada item no valor da propriedade `integral_sets` DEVE ser um objeto JSON descrevendo um conjunto de integrais, conforme descrito no restante desta secção.
No restante desta secção, o termo "objeto integral definido" referir-se-á a um item no valor da propriedade `integral_sets` do objeto Broombridge.

Cada objeto conjunto integral MUST tem uma propriedade `metadata` cujo valor é um objeto JSON.
O valor de `metadata` pode ser o objeto JSON vazio (isto é, `{}`), ou MAIO contém propriedades adicionais definidas pelo implementador.

### <a name="hamiltonian-section"></a>Secção Hamiltonian ###

#### <a name="overview"></a>Descrição geral ####

Esta secção é informativa.

A propriedade `hamiltonian` de cada objeto conjunto integral descreve o Hamiltonian para um problema particular de química quântica, enumerando os seus termos de um e dois corpos como matrizes escassas de números reais.
Os operadores hamiltonianos descritos por cada objeto conjunto integral tomam a forma

$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\\\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i ,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$

aqui $h_{ijkl}= (ijkl)$ na convenção de Mulliken.

Para clareza, o termo um-electrão é

$$ h_{ij} = \int {\mathrm d}x \psi^*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{;x-x\_A}  \direita) \psi\_j(x), $$

e o termo de dois eletrões é

$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_(x\_1)\psi\_j(x\_1) \frac\{1\}\|\{ x\_1 -x\_2\|\}\_k^\{\*\}(x\_2) \psi\_l(x\_2).
$$

Como notado na nossa descrição da [propriedade`basis_set`](#basis-set-object) de cada elemento da propriedade `integral_sets`, assumimos explicitamente que as funções base utilizadas são de valor real.
Isto permite-nos usar as seguintes simetrias entre os termos para comprimir a representação do Hamiltoniano.

$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.
$$


#### <a name="contents"></a>Conteúdos ####

Esta secção é normativa.

Cada conjunto integral MUST tem uma propriedade `hamiltonian` cujo valor é um objeto JSON.
O valor da propriedade `hamiltonian` é conhecido como um objeto hamiltoniano, e MUST tem as propriedades `one_electron_integrals` e `two_electron_integrals` como descrito no restante desta secção.
Um objeto hamiltoniano may também tem uma propriedade `particle_hole_representation`.
Se presente, o valor da `particle_hole_representation` DEVE seguir o formato descrito no restante desta secção.

##### <a name="one-electron-integrals-object"></a>Objeto integral de um eletrão #####

Esta secção é normativa.

A propriedade `one_electron_integrals` do objeto hamiltoniano DEVE ser uma quantidade escassa de matriz cujos índices são dois inteiros e cujos valores são números.
Todos os mandatos devem ter índices `[i, j]` onde `i >= j`.

> [NOTA] Isto reflete a simetria que $h_{ij} = h_{ji}$ que é uma consequência do facto de o Hamiltoniano ser Hermitiano.


###### <a name="example"></a>Exemplo ######

Esta secção é informativa.

A seguinte quantidade de matriz escassa representa o Hamiltonian $$ H = \left (-5.0 (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\\\downarrow})+ 0,17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2 ,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})à direita)\\(\mathrm{Ha}).
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
> Broombridge usa índice seleção de 1.


##### <a name="two-electron-integrals-object"></a>Objeto integral de dois eletrões #####

Esta secção é normativa.

A propriedade `two_electron_integrals` do objeto Hamiltonian DEVE ser uma quantidade escassa de matriz com uma propriedade adicional chamada `index_convention`.
Cada elemento do valor do `two_electron_integrals` DEVE tem quatro índices.

Cada `two_electron_integrals` propriedade DEVE ter uma propriedade `index_convention`.
O valor da propriedade `index_convention` DEVE ser um dos valores permitidos enumerados no Quadro 1.
Se o valor da `index_convention` for `mulliken`, então para cada elemento da quantidade de matriz escassa `two_electron_integrals`, um parser carregando um documento broombridge MUST instantaneamente um termo Hamiltonian igual ao operador de dois eletrões $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, onde $i$, $j$, $k$, e $l$ MUST ser inteiros na gama inclusiva de 1 a o número de eletrões especificados pela propriedade `n_electrons` do objeto conjunto integral, e onde $h_{i, j , k, l}$ é o elemento `[i, j, k, l, h(i, j, k, l)]` da quantidade escassa da matriz.

###### <a name="symmetries"></a>Simetrias ######

Esta secção é normativa.

Se a propriedade `index_convention` de um objeto `two_electron_integrals` for igual a `mulliken`, então se estiver presente um elemento com índices `[i, j, k, l]`, os seguintes índices não devem estar presentes a menos que sejam iguais a `[i, j, k, l]`:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Como a propriedade `index_convention` é um objeto de quantidade escassa, nenhum índice pode ser repetido em diferentes elementos.
> Em particular, se um elemento com índices `[i, j, k, l]` estiver presente, nenhum outro elemento pode ter esses índices.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Exemplo #######

Esta secção é informativa.

O seguinte objeto especifica o Hamiltonian

$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1,6 a{\dagger}\_{1,\sigma} a^{\dagger}\_{1,rho} a\_{1,rho} a\_{1,sigma}- 0,1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma}\_\_a{\a .\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^\_{\a 6,\rho} um\_{2,\rho} um\_{3,\sigma} $$-0,1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0,1a^\\_a.a ,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,rho} um\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\"\textrm{Ha}.
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

##### <a name="particlehole-representation-object"></a>Objeto de representação de buraco de partícula #####

Esta secção é normativa.

O objeto de representação de buracos de partículas especifica que os integrais armazenados são definidos no que diz respeito à representação de buracos de partículas, onde os operadores de criação e aniquilação descrevem as excitações longe do estado de referência utilizado, como um Hartree. Estado de Fock.
O objeto é OPCIONAL.
Se o objeto não for especificado, o Hamiltonian deve ser interpretado como não dado na representação de buracos de partículas.
Se presente, o valor da `particle_hole_representation` DEVE ser um objeto de quantidade escassa cujos índices são quatro inteiros, e cujos valores são um número e uma corda.
A parte da cadeia do valor de cada elemento DEVE conter apenas os caracteres `'+'` e `'-'` que especifica se um determinado fator no termo é um operador de criação ou aniquilação na representação do buraco de partículas.  Por exemplo, `"-+++"` responde a um buraco criado no local $i$ e partículas sendo criadas em locais $j, k$ e $l$.

> [!NOTE]
> Dado que o valor da `particle_hole_representation` é um objeto de quantidade escassa de matriz, as propriedades `unit` e `format` devem ser especificadas.
> As unidades aceitáveis incluem a lista do quadro 1.
> A propriedade `format` é necessária, e indica se os coeficientes hamiltonianos são especificados como uma matriz densa ou escassa.
> Na versão atual, apenas são suportadas matrizes escassas, com a interpretação de que todos os elementos não especificados são $0$, mas futuras versões podem adicionar suporte para valores adicionais da propriedade `format`.

### <a name="initial-state-section"></a>Secção inicial do Estado ###

O initial_state_suggestion objeto especifica os estados quânticos iniciais de interesse para o hamiltoniano especificado. Este objeto deve ser uma variedade de objetos `state` JSON.

#### <a name="state-object"></a>Objeto de Estado ####

Cada estado representa uma superposição de orbitais ocupados. Cada objeto de estado DEVE ter uma propriedade `label` contendo uma corda. Cada objeto de Estado DEVE ter uma propriedade `superposition` contendo uma série de estados de base e as suas amplitudes não normalizadas.

Por exemplo, os estados iniciais $$ \ket {G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a{\dagger}\_2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}$$ $$ \ket{E}=\frac{{{\_{{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow}}}0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow}}{sqrt{0.1^2+/0,{0} 2 por
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

#### <a name="basis-set-object"></a>Objeto de conjunto de base ####

Esta secção é normativa.

Cada objeto conjunto integral PODE ter uma propriedade `basis_set`.
Se presente, o valor da propriedade `basis_set` DEVE ser um objeto com duas propriedades, `type` e `name`.

As funções base identificadas pelo valor do `basis_set` imóvel DEVEM ser avaliadas em real.

> [!NOTE]
> O pressuposto de que todas as funções base são de valor real pode ser relaxado em futuras versões desta especificação.

## <a name="tables-and-lists"></a>Tabelas e Listas ##

### <a name="table-1-allowed-physical-units"></a>Mesa 1. Unidades Físicas Permitidas ###

Esta secção é normativa.

Qualquer cadeia que especifique uma unidade DEVE ser uma das seguintes:

- `hartree`
- `ev`

Os parsers e os produtores devem tratar os seguintes objetos de quantidade simples como equivalentes:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Mesa 2. Convenções de índice sinuosas ###

Esta secção é normativa.

Qualquer cadeia que especifique uma convenção de índice deve ser uma das seguintes:

- `mulliken`

Esta secção é informativa.

As convenções de índiceadicionais podem ser introduzidas em futuras versões desta especificação.

#### <a name="interpretation-of-index-conventions"></a>Interpretação das Convenções de Índices ####

Esta secção é informativa.
