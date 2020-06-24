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
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="4c3c6-103">Carregar e classificar os seus próprios conjuntos de dados</span><span class="sxs-lookup"><span data-stu-id="4c3c6-103">Load and classify your own datasets</span></span>

<span data-ttu-id="4c3c6-104">Neste pequeno tutorial, vamos aprender a carregar o seu próprio conjunto de dados para treinar um modelo de classificador com o Kit de Desenvolvimento Quântico (QDK).</span><span class="sxs-lookup"><span data-stu-id="4c3c6-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="4c3c6-105">Recomendamos vivamente a utilização de um formato de serialização padronizado, como [ficheiros JSON,](https://en.wikipedia.org/wiki/JSON) para armazenar os seus dados.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="4c3c6-106">Estes formatos oferecem alta compatibilidade com diferentes estruturas como python e o ecossistema .NET.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="4c3c6-107">Em particular, recomendamos a utilização do nosso modelo para o carregamento dos dados, para que possa copiar o código diretamente das amostras.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="4c3c6-108">Modelo para carregar os seus conjuntos de dados</span><span class="sxs-lookup"><span data-stu-id="4c3c6-108">Template for loading your datasets</span></span>

<span data-ttu-id="4c3c6-109">Suponha que temos um conjunto de dados de treino $(x, y)$ de tamanho $N=2$ onde cada instância $x_i$ de $x$ tem três características: $x_{i1}$, $x_{i2}$ e $x_{i3}$.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="4c3c6-110">O conjunto de dados de validação tem a mesma estrutura.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="4c3c6-111">Estes datsets podem ser representados por um `data.json` ficheiro semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c3c6-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

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

### <a name="example-using-the-template"></a><span data-ttu-id="4c3c6-112">Exemplo usando o modelo</span><span class="sxs-lookup"><span data-stu-id="4c3c6-112">Example using the template</span></span>

<span data-ttu-id="4c3c6-113">Suponha que temos um pequeno conjunto de dados com as alturas e pesos de diferentes gatos e cães.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="4c3c6-114">Este conjunto de dados é muito pequeno para treinar um modelo, mas será suficiente para mostrar o processo de carregamento de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="4c3c6-115">Altura (m)</span><span class="sxs-lookup"><span data-stu-id="4c3c6-115">Height (m)</span></span> | <span data-ttu-id="4c3c6-116">Peso (kg)</span><span class="sxs-lookup"><span data-stu-id="4c3c6-116">Weight (kg)</span></span> | <span data-ttu-id="4c3c6-117">Animal</span><span class="sxs-lookup"><span data-stu-id="4c3c6-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="4c3c6-118">0.54</span><span class="sxs-lookup"><span data-stu-id="4c3c6-118">0.54</span></span>      | <span data-ttu-id="4c3c6-119">30</span><span class="sxs-lookup"><span data-stu-id="4c3c6-119">30</span></span>         | <span data-ttu-id="4c3c6-120">Cão</span><span class="sxs-lookup"><span data-stu-id="4c3c6-120">Dog</span></span>    |
| <span data-ttu-id="4c3c6-121">0.30</span><span class="sxs-lookup"><span data-stu-id="4c3c6-121">0.30</span></span>      | <span data-ttu-id="4c3c6-122">8</span><span class="sxs-lookup"><span data-stu-id="4c3c6-122">8</span></span>          | <span data-ttu-id="4c3c6-123">Gato</span><span class="sxs-lookup"><span data-stu-id="4c3c6-123">Cat</span></span>    |
| <span data-ttu-id="4c3c6-124">0,91</span><span class="sxs-lookup"><span data-stu-id="4c3c6-124">0.91</span></span>      | <span data-ttu-id="4c3c6-125">44</span><span class="sxs-lookup"><span data-stu-id="4c3c6-125">44</span></span>         | <span data-ttu-id="4c3c6-126">Cão</span><span class="sxs-lookup"><span data-stu-id="4c3c6-126">Dog</span></span>    |
| <span data-ttu-id="4c3c6-127">0.86</span><span class="sxs-lookup"><span data-stu-id="4c3c6-127">0.86</span></span>      | <span data-ttu-id="4c3c6-128">31</span><span class="sxs-lookup"><span data-stu-id="4c3c6-128">31</span></span>          | <span data-ttu-id="4c3c6-129">Cão</span><span class="sxs-lookup"><span data-stu-id="4c3c6-129">Dog</span></span>    |
| <span data-ttu-id="4c3c6-130">0.32</span><span class="sxs-lookup"><span data-stu-id="4c3c6-130">0.32</span></span>      | <span data-ttu-id="4c3c6-131">5</span><span class="sxs-lookup"><span data-stu-id="4c3c6-131">5</span></span>         | <span data-ttu-id="4c3c6-132">Gato</span><span class="sxs-lookup"><span data-stu-id="4c3c6-132">Cat</span></span>    |
| <span data-ttu-id="4c3c6-133">0,25</span><span class="sxs-lookup"><span data-stu-id="4c3c6-133">0.25</span></span>      | <span data-ttu-id="4c3c6-134">4</span><span class="sxs-lookup"><span data-stu-id="4c3c6-134">4</span></span>          | <span data-ttu-id="4c3c6-135">Gato</span><span class="sxs-lookup"><span data-stu-id="4c3c6-135">Cat</span></span>    |

<span data-ttu-id="4c3c6-136">O processo é:</span><span class="sxs-lookup"><span data-stu-id="4c3c6-136">The process is:</span></span>

- <span data-ttu-id="4c3c6-137">Primeiro, temos de separar o conjunto de dados em treino e validação.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="4c3c6-138">Neste caso, podemos apenas recolher as três primeiras amostras para o treino e as restantes amostras para validação.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="4c3c6-139">Em geral, é uma boa prática recolher aleatoriamente o conjunto de dados de formação e validação para evitar distorções indesejadas nos dados de formação.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="4c3c6-140">Em segundo lugar, temos de atribuir um rótulo numérico a cada turma.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="4c3c6-141">Note que, para já, a biblioteca QML só admite problemas de classificação binária.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="4c3c6-142">Por isso, atribuímos a etiqueta 0 à classe `Dog` e o número 1 à `Cat` turma.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="4c3c6-143">Finalmente, preenchemos o modelo usando os dados do nosso conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="4c3c6-144">Note que para os grandes conjuntos de dados deve construir um pequeno script para gerar automaticamente o modelo a partir do seu conjunto de dados específico.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="4c3c6-145">Este script dependerá do formato original do seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="4c3c6-146">Para o nosso conjunto de dados, o `data.json` ficheiro é:</span><span class="sxs-lookup"><span data-stu-id="4c3c6-146">For our dataset the `data.json` file is:</span></span>

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

## <a name="loading-the-data"></a><span data-ttu-id="4c3c6-147">Carregar os dados</span><span class="sxs-lookup"><span data-stu-id="4c3c6-147">Loading the data</span></span>

<span data-ttu-id="4c3c6-148">Uma vez que tenha os seus dados serializados como um ficheiro JSON, pode carregá-lo na utilização de bibliotecas JSON fornecidas com o seu idioma de escolha de anfitrião.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="4c3c6-149">Python</span><span class="sxs-lookup"><span data-stu-id="4c3c6-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="4c3c6-150">Python fornece o [ `json` pacote incorporado](https://docs.python.org/3.7/library/json.html) para trabalhar com dados serializados JSON:</span><span class="sxs-lookup"><span data-stu-id="4c3c6-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="4c3c6-151">C#</span><span class="sxs-lookup"><span data-stu-id="4c3c6-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="4c3c6-152">A plataforma .NET Core fornece o [ `System.Text.Json` pacote](https://www.nuget.org/packages/System.Text.Json) para trabalhar com dados serializados da JSON:</span><span class="sxs-lookup"><span data-stu-id="4c3c6-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="4c3c6-153">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="4c3c6-153">Next steps</span></span>

<span data-ttu-id="4c3c6-154">Agora está pronto para começar a fazer as suas próprias experiências com os seus próprios conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="4c3c6-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="4c3c6-155">Experimente diferentes classificadores e conjunto de dados e contribua para que a comunidade partilhe os seus resultados!</span><span class="sxs-lookup"><span data-stu-id="4c3c6-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
