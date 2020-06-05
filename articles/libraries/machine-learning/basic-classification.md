---
title: Classificação básica com a biblioteca quantum machine learning
description: Aprenda a executar um classificador sequencial quântico escrito em Q# utilizando a biblioteca Quantum Machine Learning do Microsoft QDK.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422177"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="44f0e-103">Classificação básica: Classificar os dados com o QDK</span><span class="sxs-lookup"><span data-stu-id="44f0e-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="44f0e-104">Neste Quickstart, aprenderás a executar um classificador sequencial quântico escrito em Q# utilizando a biblioteca Quantum Machine Learning do QDK.</span><span class="sxs-lookup"><span data-stu-id="44f0e-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="44f0e-105">Neste guia utilizaremos o conjunto de dados de meia-lua, utilizando uma estrutura de classificador definida em Q#.</span><span class="sxs-lookup"><span data-stu-id="44f0e-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44f0e-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="44f0e-106">Prerequisites</span></span>

- <span data-ttu-id="44f0e-107">O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="44f0e-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="44f0e-108">Crie um projeto Q# para um [programa de anfitrião Python](xref:microsoft.quantum.install.python) ou um programa de [anfitrião C](xref:microsoft.quantum.install.cs)# .</span><span class="sxs-lookup"><span data-stu-id="44f0e-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="44f0e-109">Programa de acolhimento</span><span class="sxs-lookup"><span data-stu-id="44f0e-109">Host program</span></span>

<span data-ttu-id="44f0e-110">O seu programa de anfitriões é composto por três partes:</span><span class="sxs-lookup"><span data-stu-id="44f0e-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="44f0e-111">Carregue o conjunto de dados e escolha um conjunto de parâmetros iniciais para o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="44f0e-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="44f0e-112">Execute o treino para determinar os parâmetros e o enviesamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="44f0e-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="44f0e-113">Validar o modelo para determinar a sua precisão</span><span class="sxs-lookup"><span data-stu-id="44f0e-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="44f0e-114">Python com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="44f0e-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="44f0e-115">Para executar você é o classificador Q# de Python, guarde o seguinte código como `host.py` .</span><span class="sxs-lookup"><span data-stu-id="44f0e-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="44f0e-116">Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="44f0e-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="44f0e-117">Em seguida, pode executar o programa anfitrião do Python na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="44f0e-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="44f0e-118">C# com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="44f0e-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="44f0e-119">Para executar você é o classificador Q# de C#, guarde o seguinte código como `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="44f0e-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="44f0e-120">Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="44f0e-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="44f0e-121">Em seguida, pode executar o programa anfitrião de C# na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="44f0e-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="44f0e-122">C# com o Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="44f0e-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="44f0e-123">Para executar o seu novo programa Q# a partir de C# no Visual Studio, modifique `Host.cs` para incluir o seguinte código C#.</span><span class="sxs-lookup"><span data-stu-id="44f0e-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="44f0e-124">Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="44f0e-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="44f0e-125">Em seguida, prima F5, o programa iniciará a execução e será apresentada uma nova janela com os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="44f0e-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="44f0e-126">Código \# de classificação Q</span><span class="sxs-lookup"><span data-stu-id="44f0e-126">Q\# classifier code</span></span>

<span data-ttu-id="44f0e-127">Agora vamos ver como as operações invocadas pelo programa anfitrião são definidas em Q#.</span><span class="sxs-lookup"><span data-stu-id="44f0e-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="44f0e-128">Guardamos o seguinte código num ficheiro chamado `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="44f0e-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="44f0e-129">As funções e operações mais importantes definidas no código acima são:</span><span class="sxs-lookup"><span data-stu-id="44f0e-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="44f0e-130">`ClassifierStructure() : ControlledRotation[]`: nesta função definimos a estrutura do nosso modelo de circuito adicionando as camadas dos portões controlados que consideramos.</span><span class="sxs-lookup"><span data-stu-id="44f0e-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="44f0e-131">Este passo é análogo à declaração de camadas de neurónios num modelo sequencial de aprendizagem profunda.</span><span class="sxs-lookup"><span data-stu-id="44f0e-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="44f0e-132">`TrainHalfMoonModel() : (Double[], Double)`: esta operação é a parte central do código e define a formação.</span><span class="sxs-lookup"><span data-stu-id="44f0e-132">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="44f0e-133">Aqui carregamos as amostras do conjunto de dados incluído na biblioteca, definimos os hipermetrões e os parâmetros iniciais para o treino e começamos a formação chamando a operação `TrainSequentialClassifier` incluída na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="44f0e-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="44f0e-134">Produz os parâmetros e o enviesamento que determina o classificador.</span><span class="sxs-lookup"><span data-stu-id="44f0e-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="44f0e-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: esta operação define o processo de validação para avaliar o modelo.</span><span class="sxs-lookup"><span data-stu-id="44f0e-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="44f0e-136">Aqui carregamos as amostras para validação, o número de medições por amostra e a tolerância.</span><span class="sxs-lookup"><span data-stu-id="44f0e-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="44f0e-137">Produz o número de classificações erradas no lote escolhido de amostras para validação.</span><span class="sxs-lookup"><span data-stu-id="44f0e-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44f0e-138">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="44f0e-138">Next steps</span></span>

<span data-ttu-id="44f0e-139">Primeiro, podes jogar com o código e tentar alterar alguns parâmetros para ver como isso afeta o treino.</span><span class="sxs-lookup"><span data-stu-id="44f0e-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="44f0e-140">Em seguida, no próximo tutorial, [desenhe o seu próprio classificador,](xref:microsoft.quantum.libraries.machine-learning.design)aprenderá a definir a estrutura do classificador.</span><span class="sxs-lookup"><span data-stu-id="44f0e-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
