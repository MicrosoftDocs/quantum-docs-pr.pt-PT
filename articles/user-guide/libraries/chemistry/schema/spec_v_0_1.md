---
title: Especificação de esquema de Broombridge (ver 0.1)
description: Detalha as especificações do esquema de química quântica de Broombridge v0.1 para a biblioteca de química quântica da Microsoft.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: abbc63b8801c774e6ba06cff99b7382d64424b2c
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869142"
---
# <a name="broombridge-specification-v01"></a>Especificação de Broombridge v0.1 #

As palavras-chave "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHOULD", "SHOULD", "SHOULD", "RECOMMENDED", "MAY" e "OPTIONAL" neste documento devem ser interpretadas como descrito no [RFC 2119](https://tools.ietf.org/html/rfc2119).

Qualquer barra lateral com os títulos "NOTA", "INFORMAÇÃO" ou "AVISO" é informativa.

## <a name="introduction"></a>Introdução ##

Esta secção é informativa.

Os documentos de Broombridge destinam-se a comunicar casos de problemas de simulação na química quântica para processamento utilizando simulação quântica e cabos de ferramentas de programação.

## <a name="serialization"></a>Serialização ##

Esta secção é normativa.

Um documento de Broombridge DEVE ser serializado como um [documento YAML 1.2](http://yaml.org/spec/) que representa um objeto JSON, conforme descrito na secção [RFC 4627](https://tools.ietf.org/html/rfc4627) 2.2.
O objeto serializado para YAML MUST tem um `"$schema"` imóvel cujo valor é `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` , e DEVE ser válido de acordo com as especificações do projecto-06 do JSON Schema [[1,](https://tools.ietf.org/html/draft-wright-json-schema-01) [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Para o restante desta especificação, "o objeto Broombridge" refere-se ao objeto JSON desseserializado a partir de um documento YAML de Broombridge.

Salvo indicação em contrário, os objetos NÃO DEVEM ter propriedades adicionais para além das especificadas explicitamente neste documento.

## <a name="additional-definitions"></a>Definições Adicionais ##

Esta secção é normativa.

### <a name="quantity-objects"></a>Objetos de quantidade ###

Esta secção é normativa.

Um _objeto de quantidade_ é um objeto JSON, e DEVE ter uma propriedade cujo valor é um dos `units` valores permitidos listados na Tabela 1.

Um objeto de quantidade é um _objeto de quantidade simples_ se tiver uma única propriedade `value` além da sua `units` propriedade.
O valor do `value` imóvel DEVE ser um número.

Um objeto de quantidade é um _objeto de quantidade limitado_ se tiver as propriedades e `lower` `upper` além da sua `units` propriedade.
Os valores do `lower` e propriedades DEVEM ser `upper` números.
Um objeto de quantidade limitado pode ter uma propriedade `value` cujo valor é um número.

Um objeto de quantidade é um _objeto de quantidade de matriz escassa_ se tiver a propriedade e uma propriedade `format` `values` além da sua `units` propriedade.
O valor de `format` MUST é a `sparse` corda.
O valor do `values` imóvel DEVE ser um conjunto.
Cada elemento de `values` MUST é uma matriz que representa os índices e o valor da quantidade de matriz escassa.

Os índices para cada elemento de um objeto de quantidade de matriz escassa DEVEM ser únicos em todo o objeto de quantidade de matriz escassa.
Se um índice estiver presente com um valor de `0` , um parser MUST tratar o objeto de quantidade de matriz escassa de forma idêntica a um objeto de quantidade de matriz escasso no qual esse índice não esteja presente.


Um objeto de quantidade DEVE ser

- um simples objeto de quantidade,
- um objeto de quantidade limitado, ou
- um objeto de quantidade de matriz escassa.


### <a name="examples"></a>Exemplos ###

Esta secção é informativa.

Uma quantidade simples representando $1.9844146837 \, \mathrm{Ha}$:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Uma quantidade limitada que representa uma distribuição uniforme durante o intervalo $[-7, -6] \, \mathrm{Ha}$:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Segue-se uma quantidade de matriz escassa com um elemento `[1, 2]` igual e um elemento igual `hello` `[3, 4]` `world` a:

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

O objeto Broombridge DEVE ter uma propriedade `format` cujo valor é um objeto JSON com uma propriedade chamada `version` .
O `version` imóvel DEVE ter o `"0.1"` valor.

### <a name="example"></a>Exemplo ###

Esta secção é informativa.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Secção de conjuntos integrais ##

Esta secção é normativa.

O objeto Broombridge DEVE ter uma propriedade `integral_sets` cujo valor é uma matriz JSON.
Cada item no valor da `integral_sets` propriedade DEVE ser um objeto JSON descrevendo um conjunto de integrais, conforme descrito no restante desta secção.
No restante desta secção, o termo "objeto conjunto integral" refere-se a um item no valor da `integral_sets` propriedade do objeto Broombridge.

Cada objeto conjunto integral DEVE ter uma propriedade `metadata` cujo valor é um objeto JSON.
O valor de `metadata` MAIO é o objeto JSON vazio (isto é, ) ou MAY contém propriedades `{}` adicionais definidas pelo implementor.

### <a name="hamiltonian-section"></a>Secção Hamiltoniana ###

#### <a name="overview"></a>Descrição geral ####

Esta secção é informativa.

A `hamiltonian` propriedade de cada objeto conjunto integral descreve o Hamiltonian para um problema particular de química quântica, enumerando os seus termos de um e dois corpos como conjuntos escassos de números reais.
Os operadores hamiltonianos descritos por cada objeto conjunto integral assumem a forma

$$ H = \sum \_ \{ i,j \} \sum \_ {\sigma\in \\ {\uparrow,\downarrow \\ }} h \_ \{ ij \} \{ a^ \dagger \} \_ {i,\sigma} a \_ {j,\sigma} + \frac {1} {2} \frac \sum \_ \{ i,j,k,l \} \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }} h \_ {ijkl} a^\dagger \_ {i,\sigma} a^\dagger \_ {k,\rho} a \_ {l,\rho} a \_ {j,\sigma}, $$

aqui $h_{ijkl}= (ij/kl)$ na convenção de Mulliken.

Para clareza, o termo de um eletrão é

$$ h_{ij} = \int {\mathrm d}x \psi^* \_ i(x) \esquerda \frac {1} {2} \nabla^2 + \soma \_ {A}frac{Z \_ A}{x-x \_ A[}  \direita) \psi \_ j(x), $$

e o termo de dois eletrões é

$$ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x^2 \psi^ \{ \* \} \_ i(x \_ 1)\psi \_ j(x \_ 1) \frac \{ 1 \} \{ \| x \_ \_ 1 -2 \| \} \psi \_ k^ \{ \* \} (x \_ 2) \psi \_ l(x \_ 2).
$$

Como indicado na nossa descrição da [ `basis_set` propriedade](#basis-set-object) de cada elemento do `integral_sets` imóvel, assumimos explicitamente que as funções de base utilizadas são de valor real.
Isto permite-nos usar as seguintes assimetrias entre os termos para comprimir a representação do Hamiltonian.

$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.
$$


#### <a name="contents"></a>Conteúdos ####

Esta secção é normativa.

Cada conjunto integral DEVE ter uma propriedade `hamiltonian` cujo valor é um objeto JSON.
O valor da `hamiltonian` propriedade é conhecido como um objeto hamiltoniano, e DEVE ter as propriedades e como descrito no restante desta `one_electron_integrals` `two_electron_integrals` secção.
Um objeto hamiltoniano pode também ter uma `particle_hole_representation` propriedade.
Se estiver presente, o valor de `particle_hole_representation` MUST segue o formato descrito no restante desta secção.

##### <a name="one-electron-integrals-object"></a>Objeto integral de um eletrão #####

Esta secção é normativa.

A `one_electron_integrals` propriedade do objeto Hamiltonian DEVE ser uma quantidade escassa de matriz cujos índices são dois inteiros e cujos valores são números.
Todos os termos devem ter índices `[i, j]` onde `i >= j` .

> [NOTA] Isto reflete a simetria que $h_{ij} = h_{ji}$ o que é uma consequência do facto de o Hamiltonian ser hermitiano.


###### <a name="example"></a>Exemplo ######

Esta secção é informativa.

A quantidade de matriz escassa que se segue representa o Hamiltonian $$ H = \esquerda (-5,0 (a^ \{ \dagger \} \_ {1,\uparrow} a \_ {1,\uparrow}+a^ \{ \dagger \} \_ {1,\downarrow} a \_ {1,\downarrow}+ 0,17 (a^ \{ \agger \} \_ {2,uparrow arow a arow a arow a arow a a{1\uparrow arow a a{2,uparrow arow a arow a a{2,uparrow arow a arow a arow a*downrow a a{1,\downarrow} \_ {1,\uparrow}+ a^ \{ \dagger \} \_ {1,\uparrow} a \_ {2,\uparrow}+a^ \{ \dagger \} \_ {2,\downarrow} a \_ {1,\downarrow}+ a^ \{ \dagger \} \_ {1,\downarrow} a \_ {2,\downarrow})\right) \\ \mathrm{Ha}.
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
> Broombridge usa indexação baseada em 1.


##### <a name="two-electron-integrals-object"></a>Objeto integral de dois eletrões #####

Esta secção é normativa.

A `two_electron_integrals` propriedade do objeto Hamiltonian DEVE ser uma quantidade de matriz escassa com uma propriedade adicional chamada `index_convention` .
Cada elemento do valor de `two_electron_integrals` MUST tem quatro índices.

Cada `two_electron_integrals` imóvel DEVE ter uma `index_convention` propriedade.
O valor do `index_convention` imóvel DEVE ser um dos valores permitidos listados no Quadro 1.
Se o valor for `index_convention` `mulliken` , então para cada elemento da quantidade de `two_electron_integrals` matriz escassa, um parser carregando um documento de Broombridge DEVE instantaneamente um termo Hamiltoniano igual ao operador de dois eletrões $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, onde $i$, $j$, $k$, e $l$ MUST sejam inteiros na gama inclusiva de 1 a o número de eletrões especificados pela `n_electrons` propriedade do objeto conjunto integral, e onde $h_{i, j, k, l} é o elemento `[i, j, k, l, h(i, j, k, l)]` da quantidade escassa da matriz.

###### <a name="symmetries"></a>Assimetrias ######

Esta secção é normativa.

Se a `index_convention` propriedade de um objeto for igual a , `two_electron_integrals` `mulliken` então se um elemento com índices `[i, j, k, l]` estiver presente, os seguintes índices NÃO devem estar presentes a menos que sejam iguais `[i, j, k, l]` a:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Como a `index_convention` propriedade é um objeto de quantidade escassa, nenhum índice pode ser repetido em diferentes elementos.
> Em particular, se um elemento com índices `[i, j, k, l]` estiver presente, nenhum outro elemento pode ter esses índices.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Exemplo #######

Esta secção é informativa.

O seguinte objeto especifica o Hamiltonian

$$ H = \frac12 \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }}\Biggr( 1.6 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {1,\rho} a \_ {1,\rho} a \_ {1,\rho} a {1,\a^{1,\rho} \_ a \_ \_ {3,\rho} a \_ {2,\sigma}- 0,1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {2,\rho} a \_ {3,\rho} a {3,\sigma}- 0.1 a^{\dagger} \_ {1,\a^a^} \_ {6,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0,1 a^{\dagger} \_ {1,\sigma} {{\dagger} \_ {6,\rho} a \_ {2,\rho} a \_ {3,\sigma} $$ $-0,1 a^{\dagger} \_ {3,sigma\a{\a{{2,\rho} \_ a \_ {6,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {1,\rho} a \_ {6,\sigma}- 0,1 a^{\dagger} \_ {2,\sigma} \_ .\rho} a \_ {6,\rho} a \_ {1,\sigma}- 0,1 a^{\dagger} \_ {2,\sigma} a^{\dagger} \_ {3,\rho} a \_ {1,\rho} a \_ {6,\sigma}\Biggr) \\ \textrm{Ha}.
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

##### <a name="particlehole-representation-object"></a>Objeto de representação de buraco de partículas #####

Esta secção é normativa.

O objeto de representação do buraco de partículas especifica que as integrais armazenadas são definidas no que diz respeito à representação de buracos de partículas, em que os operadores de criação e aniquilação descrevem excitações longe do estado de referência utilizado, como um estado Hartree-Fock.
O objeto é OPCIONAL.
Se o objeto não for especificado, o Hamiltonian deve ser interpretado como não dado na representação do buraco de partículas.
Se presente, o valor de `particle_hole_representation` MUST é um objeto de quantidade de matriz escassa cujos índices são quatro inteiros, e cujos valores são um número e uma corda.
A parte da cadeia do valor de cada elemento DEVE conter apenas os caracteres `'+'` e que especifica se um dado fator no termo é um operador de `'-'` criação ou aniquilação na representação do buraco de partículas.  Por `"-+++"` exemplo, os núcleos para um buraco que está a ser criado no local $i$ e partículas a serem criadas em locais $j,k$ e $l$.

> [!NOTE]
> Como o valor do `particle_hole_representation` é um objeto de quantidade de matriz escasso, as propriedades e propriedades devem ser `unit` `format` especificadas.
> Unidades aceitáveis incluem estão listadas no quadro 1.
> A `format` propriedade é necessária, e indica se os coeficientes hamiltonianos são especificados como uma matriz densa ou escassa.
> Na versão atual, apenas as matrizes escassas são suportadas, com a interpretação de que todos os elementos não especificados são $0$, mas futuras versões podem adicionar suporte para valores adicionais da `format` propriedade.

### <a name="initial-state-section"></a>Secção inicial do Estado ###

O objeto initial_state_suggestion especifica estados quânticos iniciais de interesse para o hamiltoniano especificado. Este objeto deve ser uma matriz de `state` objetos JSON.

#### <a name="state-object"></a>Objeto de Estado ####

Cada estado representa uma superposição de orbitais ocupados. Cada objeto de estado DEVE ter uma `label` propriedade contendo uma corda. Cada objeto de estado DEVE ter uma `superposition` propriedade contendo uma variedade de estados de base e suas amplitudes não normalizadas.

Por exemplo, os estados iniciais $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger} \_ {1,\uparrow}a^\dagger} \_ {2,\uparrow}}a^{\dagger} \_ {2,\downarrow})\ket {0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger} \_ {1,\uparrow}a^{\\da \_ {2,\uparrow}a^{\dagger} \_ {2,\downarrow}+0.2 (a^{\dagger} \_ {1,\uparrow}a^{\dagger} \_ {3,,,3,,3,,3,,3,,3,,3,,,I.,,\uparrow}a^{\dagger} \_ {2,\downarrow}}}{\sqrt{/0.1/0,2/0,2[2}}}\ket {0} $$ são representados por
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

Cada objeto conjunto integral pode ter uma `basis_set` propriedade.
Se estiver presente, o valor do `basis_set` imóvel DEVE ser um objeto com duas propriedades, `type` e `name` .

As funções de base identificadas pelo valor do `basis_set` imóvel MUST são de valor real.

> [!NOTE]
> O pressuposto de que todas as funções de base são valorizados real pode ser relaxado em futuras versões desta especificação.

## <a name="tables-and-lists"></a>Tabelas e Listas ##

### <a name="table-1-allowed-physical-units"></a>Tabela 1. Unidades Físicas Permitidas ###

Esta secção é normativa.

Qualquer cadeia que especifique uma unidade DEVE ser uma das seguintes:

- `hartree`
- `ev`

Os parsers e produtores DEVEM tratar os seguintes objetos de quantidade simples como equivalentes:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabela 2. Convenções de Índice Permitidas ###

Esta secção é normativa.

Qualquer cadeia que especifique uma convenção de índice DEVE ser uma das seguintes:

- `mulliken`

Esta secção é informativa.

As convenções de índice adicionais podem ser introduzidas em futuras versões desta especificação.

#### <a name="interpretation-of-index-conventions"></a>Interpretação das Convenções de Índice ####

Esta secção é informativa.
