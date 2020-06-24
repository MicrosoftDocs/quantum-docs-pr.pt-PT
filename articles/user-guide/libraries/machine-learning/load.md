---
title: Carregar dados clássicos
description: Aprenda a carregar o seu próprio conjunto de dados para treinar um modelo de classificador com o Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: efa4a65a489446cbef48507d0b02a932da74c71c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276138"
---
# <a name="load-and-classify-your-own-datasets"></a>Carregar e classificar os seus próprios conjuntos de dados

Neste pequeno tutorial, vamos aprender a carregar o seu próprio conjunto de dados para treinar um modelo de classificador com o Kit de Desenvolvimento Quântico (QDK).

Recomendamos vivamente a utilização de um formato de serialização padronizado, como [ficheiros JSON,](https://en.wikipedia.org/wiki/JSON) para armazenar os seus dados.
Estes formatos oferecem alta compatibilidade com diferentes estruturas como python e o ecossistema .NET.
Em particular, recomendamos a utilização do nosso modelo para o carregamento dos dados, para que possa copiar o código diretamente das amostras.

## <a name="template-for-loading-your-datasets"></a>Modelo para carregar os seus conjuntos de dados

Suponha que temos um conjunto de dados de treino $(x, y)$ de tamanho $N=2$ onde cada instância $x_i$ de $x$ tem três características: $x_{i1}$, $x_{i2}$ e $x_{i3}$.
O conjunto de dados de validação tem a mesma estrutura.
Estes datsets podem ser representados por um `data.json` ficheiro semelhante ao seguinte:

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Exemplo usando o modelo

Suponha que temos um pequeno conjunto de dados com as alturas e pesos de diferentes gatos e cães. Este conjunto de dados é muito pequeno para treinar um modelo, mas será suficiente para mostrar o processo de carregamento de um conjunto de dados.

| Altura (m) | Peso (kg) | Animal |
|-----------|------------|--------|
| 0.54      | 30         | Cão    |
| 0.30      | 8          | Gato    |
| 0,91      | 44         | Cão    |
| 0.86      | 31          | Cão    |
| 0.32      | 5         | Gato    |
| 0,25      | 4          | Gato    |

O processo é:

- Primeiro, temos de separar o conjunto de dados em treino e validação. Neste caso, podemos apenas recolher as três primeiras amostras para o treino e as restantes amostras para validação. Em geral, é uma boa prática recolher aleatoriamente o conjunto de dados de formação e validação para evitar distorções indesejadas nos dados de formação.
- Em segundo lugar, temos de atribuir um rótulo numérico a cada turma. Note que, para já, a biblioteca QML só admite problemas de classificação binária. Por isso, atribuímos a etiqueta 0 à classe `Dog` e o número 1 à `Cat` turma.
- Finalmente, preenchemos o modelo usando os dados do nosso conjunto de dados. Note que para os grandes conjuntos de dados deve construir um pequeno script para gerar automaticamente o modelo a partir do seu conjunto de dados específico. Este script dependerá do formato original do seu conjunto de dados.

Para o nosso conjunto de dados, o `data.json` ficheiro é:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Carregar os dados

Uma vez que tenha os seus dados serializados como um ficheiro JSON, pode carregá-lo na utilização de bibliotecas JSON fornecidas com o seu idioma de escolha de anfitrião.

### <a name="python"></a>[Python](#tab/tabid-python)

Python fornece o [ `json` pacote incorporado](https://docs.python.org/3.7/library/json.html) para trabalhar com dados serializados JSON:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

A plataforma .NET Core fornece o [ `System.Text.Json` pacote](https://www.nuget.org/packages/System.Text.Json) para trabalhar com dados serializados da JSON:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Passos seguintes

Agora está pronto para começar a fazer as suas próprias experiências com os seus próprios conjuntos de dados. Experimente diferentes classificadores e conjunto de dados e contribua para que a comunidade partilhe os seus resultados!
