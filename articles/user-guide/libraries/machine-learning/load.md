---
title: Carregar dados clássicos
description: Aprenda a carregar o seu próprio conjunto de dados para treinar um modelo de classificador com o Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868836"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="f05b1-103">Carregar e classificar os seus próprios conjuntos de dados</span><span class="sxs-lookup"><span data-stu-id="f05b1-103">Load and classify your own datasets</span></span>

<span data-ttu-id="f05b1-104">Neste pequeno tutorial, vamos aprender a carregar o seu próprio conjunto de dados para treinar um modelo de classificador com o Kit de Desenvolvimento Quântico (QDK).</span><span class="sxs-lookup"><span data-stu-id="f05b1-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="f05b1-105">Recomendamos vivamente a utilização de um formato de serialização padronizado, como [ficheiros JSON,](https://en.wikipedia.org/wiki/JSON) para armazenar os seus dados.</span><span class="sxs-lookup"><span data-stu-id="f05b1-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="f05b1-106">Estes formatos oferecem alta compatibilidade com diferentes estruturas como python e o ecossistema .NET.</span><span class="sxs-lookup"><span data-stu-id="f05b1-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="f05b1-107">Em particular, recomendamos a utilização do nosso modelo para o carregamento dos dados, para que possa copiar o código diretamente das amostras.</span><span class="sxs-lookup"><span data-stu-id="f05b1-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="f05b1-108">Modelo para carregar os seus conjuntos de dados</span><span class="sxs-lookup"><span data-stu-id="f05b1-108">Template for loading your datasets</span></span>

<span data-ttu-id="f05b1-109">Suponha que temos um conjunto de dados de treino $(x, y)$ de tamanho $N=2$ onde cada instância $x_i$ de $x$ tem três características: $x_{i1}$, $x_{i2}$ e $x_{i3}$.</span><span class="sxs-lookup"><span data-stu-id="f05b1-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="f05b1-110">O conjunto de dados de validação tem a mesma estrutura.</span><span class="sxs-lookup"><span data-stu-id="f05b1-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="f05b1-111">Estes datsets podem ser representados por um `data.json` ficheiro semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="f05b1-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

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

### <a name="example-using-the-template"></a><span data-ttu-id="f05b1-112">Exemplo usando o modelo</span><span class="sxs-lookup"><span data-stu-id="f05b1-112">Example using the template</span></span>

<span data-ttu-id="f05b1-113">Suponha que temos um pequeno conjunto de dados com as alturas e pesos de diferentes gatos e cães.</span><span class="sxs-lookup"><span data-stu-id="f05b1-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="f05b1-114">Este conjunto de dados é muito pequeno para treinar um modelo, mas será suficiente para mostrar o processo de carregamento de um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="f05b1-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="f05b1-115">Altura (m)</span><span class="sxs-lookup"><span data-stu-id="f05b1-115">Height (m)</span></span> | <span data-ttu-id="f05b1-116">Peso (kg)</span><span class="sxs-lookup"><span data-stu-id="f05b1-116">Weight (kg)</span></span> | <span data-ttu-id="f05b1-117">Animal</span><span class="sxs-lookup"><span data-stu-id="f05b1-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="f05b1-118">0,54</span><span class="sxs-lookup"><span data-stu-id="f05b1-118">0.54</span></span>      | <span data-ttu-id="f05b1-119">30</span><span class="sxs-lookup"><span data-stu-id="f05b1-119">30</span></span>         | <span data-ttu-id="f05b1-120">Cão</span><span class="sxs-lookup"><span data-stu-id="f05b1-120">Dog</span></span>    |
| <span data-ttu-id="f05b1-121">0.30</span><span class="sxs-lookup"><span data-stu-id="f05b1-121">0.30</span></span>      | <span data-ttu-id="f05b1-122">8</span><span class="sxs-lookup"><span data-stu-id="f05b1-122">8</span></span>          | <span data-ttu-id="f05b1-123">Gato</span><span class="sxs-lookup"><span data-stu-id="f05b1-123">Cat</span></span>    |
| <span data-ttu-id="f05b1-124">0,91</span><span class="sxs-lookup"><span data-stu-id="f05b1-124">0.91</span></span>      | <span data-ttu-id="f05b1-125">44</span><span class="sxs-lookup"><span data-stu-id="f05b1-125">44</span></span>         | <span data-ttu-id="f05b1-126">Cão</span><span class="sxs-lookup"><span data-stu-id="f05b1-126">Dog</span></span>    |
| <span data-ttu-id="f05b1-127">0.86</span><span class="sxs-lookup"><span data-stu-id="f05b1-127">0.86</span></span>      | <span data-ttu-id="f05b1-128">31</span><span class="sxs-lookup"><span data-stu-id="f05b1-128">31</span></span>          | <span data-ttu-id="f05b1-129">Cão</span><span class="sxs-lookup"><span data-stu-id="f05b1-129">Dog</span></span>    |
| <span data-ttu-id="f05b1-130">0.32</span><span class="sxs-lookup"><span data-stu-id="f05b1-130">0.32</span></span>      | <span data-ttu-id="f05b1-131">5</span><span class="sxs-lookup"><span data-stu-id="f05b1-131">5</span></span>         | <span data-ttu-id="f05b1-132">Gato</span><span class="sxs-lookup"><span data-stu-id="f05b1-132">Cat</span></span>    |
| <span data-ttu-id="f05b1-133">0,25</span><span class="sxs-lookup"><span data-stu-id="f05b1-133">0.25</span></span>      | <span data-ttu-id="f05b1-134">4</span><span class="sxs-lookup"><span data-stu-id="f05b1-134">4</span></span>          | <span data-ttu-id="f05b1-135">Gato</span><span class="sxs-lookup"><span data-stu-id="f05b1-135">Cat</span></span>    |

<span data-ttu-id="f05b1-136">O processo é:</span><span class="sxs-lookup"><span data-stu-id="f05b1-136">The process is:</span></span>

- <span data-ttu-id="f05b1-137">Primeiro, temos de separar o conjunto de dados em treino e validação.</span><span class="sxs-lookup"><span data-stu-id="f05b1-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="f05b1-138">Neste caso, podemos apenas recolher as três primeiras amostras para o treino e as restantes amostras para validação.</span><span class="sxs-lookup"><span data-stu-id="f05b1-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="f05b1-139">Em geral, é uma boa prática recolher aleatoriamente o conjunto de dados de formação e validação para evitar distorções indesejadas nos dados de formação.</span><span class="sxs-lookup"><span data-stu-id="f05b1-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="f05b1-140">Em segundo lugar, temos de atribuir um rótulo numérico a cada turma.</span><span class="sxs-lookup"><span data-stu-id="f05b1-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="f05b1-141">Note que, para já, a biblioteca QML só admite problemas de classificação binária.</span><span class="sxs-lookup"><span data-stu-id="f05b1-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="f05b1-142">Por isso, atribuímos a etiqueta 0 à classe `Dog` e o número 1 à `Cat` turma.</span><span class="sxs-lookup"><span data-stu-id="f05b1-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="f05b1-143">Finalmente, preenchemos o modelo usando os dados do nosso conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="f05b1-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="f05b1-144">Note que para os grandes conjuntos de dados deve construir um pequeno script para gerar automaticamente o modelo a partir do seu conjunto de dados específico.</span><span class="sxs-lookup"><span data-stu-id="f05b1-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="f05b1-145">Este script dependerá do formato original do seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="f05b1-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="f05b1-146">Para o nosso conjunto de dados, o `data.json` ficheiro é:</span><span class="sxs-lookup"><span data-stu-id="f05b1-146">For our dataset the `data.json` file is:</span></span>

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

## <a name="loading-the-data"></a><span data-ttu-id="f05b1-147">Carregar os dados</span><span class="sxs-lookup"><span data-stu-id="f05b1-147">Loading the data</span></span>

<span data-ttu-id="f05b1-148">Uma vez que tenha os seus dados serializados como um ficheiro JSON, pode carregá-lo na utilização de bibliotecas JSON fornecidas com o seu idioma de escolha de anfitrião.</span><span class="sxs-lookup"><span data-stu-id="f05b1-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="f05b1-149">Python</span><span class="sxs-lookup"><span data-stu-id="f05b1-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="f05b1-150">Python fornece o [ `json` pacote incorporado](https://docs.python.org/3.7/library/json.html) para trabalhar com dados serializados JSON:</span><span class="sxs-lookup"><span data-stu-id="f05b1-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="f05b1-151">C#</span><span class="sxs-lookup"><span data-stu-id="f05b1-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="f05b1-152">A plataforma .NET Core fornece o [ `System.Text.Json` pacote](https://www.nuget.org/packages/System.Text.Json) para trabalhar com dados serializados da JSON:</span><span class="sxs-lookup"><span data-stu-id="f05b1-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="f05b1-153">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="f05b1-153">Next steps</span></span>

<span data-ttu-id="f05b1-154">Agora está pronto para começar a fazer as suas próprias experiências com os seus próprios conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="f05b1-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="f05b1-155">Experimente diferentes classificadores e conjunto de dados e contribua para que a comunidade partilhe os seus resultados!</span><span class="sxs-lookup"><span data-stu-id="f05b1-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
