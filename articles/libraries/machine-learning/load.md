---
title: Carregar dados clássicos
description: Aprenda a carregar o seu próprio conjunto de dados para treinar um modelo de classificação com o Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: 15e63ced6223759a332ce22a43c133a7899f482a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909964"
---
# <a name="load-and-classify-your-own-datasets"></a>Carregue e classifique os seus próprios conjuntos de dados

Neste curto tutorial, vamos aprender a carregar o seu próprio conjunto de dados para treinar um modelo de classificação com o Quantum Development Kit (QDK).

Recomendamos vivamente a utilização de um formato de serialização padronizado, como [ficheiros JSON,](https://en.wikipedia.org/wiki/JSON) para armazenar os seus dados.
Estes formatos oferecem alta compatibilidade com diferentes quadros como python e o ecossistema .NET.
Em particular, recomendamos a utilização do nosso modelo para carregar os dados, para que possa copiar o código diretamente a partir das amostras.

## <a name="template-for-loading-your-datasets"></a>Modelo para carregar os seus conjuntos de dados

Suponha que temos um conjunto de dados de treino $(x, y)$ de tamanho $N=2$ onde cada instância $x_i$ de $x$ tem três funcionalidades: $x_{i1}$, $x_{i2}$ e $x_{i3}$.
O conjunto de dados de validação tem a mesma estrutura.
Estes datsets podem ser representados por um ficheiro `data.json` semelhante ao seguinte:

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
| 0.25      | 4          | Gato    |

O processo é:

- Primeiro, temos de separar o conjunto de dados em formação e validação. Neste caso, podemos apenas recolher as três primeiras amostras para treino e o resto das amostras para validação. Em geral, é uma boa prática provar aleatoriamente o conjunto de dados de formação e validação para evitar preconceitos indesejados nos dados de formação.
- Em segundo lugar, temos de atribuir um rótulo numérico a cada classe. Note que, por enquanto, a biblioteca QML apenas admite problemas de classificação binárias. Por isso, atribuiremos o rótulo 0 à classe `Dog` e o número 1 à classe `Cat`.
- Finalmente, preenchemos o modelo usando os dados do nosso conjunto de dados. Note que para grandes conjuntos de dados deve construir um pequeno script para gerar automaticamente o modelo a partir do seu conjunto de dados específico. Este script dependerá do formato original do seu conjunto de dados.

Para o nosso conjunto de dados, o ficheiro `data.json` é:

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

Uma vez que tenha os seus dados serializados como um ficheiro JSON, pode carregá-lo utilizando bibliotecas JSON fornecidas com a sua linguagem de eleição hospedeira.

### <a name="python"></a>[python](#tab/tabid-python)

Python fornece o [pacote de `json` incorporado](https://docs.python.org/3.7/library/json.html) para trabalhar com dados serializados pela JSON:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

A plataforma .NET Core fornece o [pacote`System.Text.Json`](https://www.nuget.org/packages/System.Text.Json) para trabalhar com dados serializados pela JSON:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="whats-next"></a>Passos seguintes?

Agora está pronto para começar a executar as suas próprias experiências com os seus próprios conjuntos de dados. Experimente diferentes classificadores e conjunto de dados e contribua para que a comunidade partilhe os seus resultados!
