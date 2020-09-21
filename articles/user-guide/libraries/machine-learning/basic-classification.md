---
title: Classificação básica com a biblioteca quantum machine learning
description: Aprenda a executar um classificador sequencial quântico escrito na Q# utilização da biblioteca Quantum Machine Learning do Microsoft QDK.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5dc4614b9992e2c6b9f8ff4b839c0929ec8cab7c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833718"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="a06e4-103">Classificação básica: Classificar os dados com o QDK</span><span class="sxs-lookup"><span data-stu-id="a06e4-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="a06e4-104">Neste Quickstart, você aprenderá a executar um classificador sequencial quântico escrito na Q# utilização da biblioteca Quantum Machine Learning do QDK.</span><span class="sxs-lookup"><span data-stu-id="a06e4-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="a06e4-105">Neste guia utilizaremos o conjunto de dados de meia-lua, utilizando uma estrutura de classificador definida em Q# .</span><span class="sxs-lookup"><span data-stu-id="a06e4-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a06e4-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a06e4-106">Prerequisites</span></span>

- <span data-ttu-id="a06e4-107">O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="a06e4-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="a06e4-108">Crie um Q# projeto para um programa de [anfitrião Python](xref:microsoft.quantum.install.python) ou um programa de [anfitrião C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="a06e4-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="a06e4-109">Programa de acolhimento</span><span class="sxs-lookup"><span data-stu-id="a06e4-109">Host program</span></span>

<span data-ttu-id="a06e4-110">O seu programa de anfitriões é composto por três partes:</span><span class="sxs-lookup"><span data-stu-id="a06e4-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="a06e4-111">Carregue o conjunto de dados e escolha um conjunto de parâmetros iniciais para o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="a06e4-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="a06e4-112">Executar treino para determinar os parâmetros e o enviesamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="a06e4-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="a06e4-113">Validar o modelo para determinar a sua precisão</span><span class="sxs-lookup"><span data-stu-id="a06e4-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="a06e4-114">Python com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="a06e4-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="a06e4-115">Para executar você é o Q# classificador de Python, guarde o seguinte código como `host.py` .</span><span class="sxs-lookup"><span data-stu-id="a06e4-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="a06e4-116">Lembre-se que também precisa do Q# ficheiro que é explicado mais tarde neste `Training.qs` tutorial.</span><span class="sxs-lookup"><span data-stu-id="a06e4-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="a06e4-117">Em seguida, pode executar o programa anfitrião do Python na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="a06e4-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="a06e4-118">C# com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="a06e4-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="a06e4-119">Para executar você é o Q# classificador de C#, guarde o seguinte código como `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="a06e4-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="a06e4-120">Lembre-se que também precisa do Q# ficheiro que é explicado mais tarde neste `Training.qs` tutorial.</span><span class="sxs-lookup"><span data-stu-id="a06e4-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="a06e4-121">Em seguida, pode executar o programa anfitrião de C# na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="a06e4-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="a06e4-122">C# com o Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a06e4-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="a06e4-123">Para executar o seu novo Q# programa a partir de C# no Visual Studio, modifique para incluir o seguinte código `Host.cs` C#.</span><span class="sxs-lookup"><span data-stu-id="a06e4-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="a06e4-124">Lembre-se que também precisa do Q# ficheiro que é explicado mais tarde neste `Training.qs` tutorial.</span><span class="sxs-lookup"><span data-stu-id="a06e4-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="a06e4-125">Prima F5 e o programa começará a funcionar.</span><span class="sxs-lookup"><span data-stu-id="a06e4-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="a06e4-126">Uma nova janela apresentará os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="a06e4-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="a06e4-127">Código \# de classificação Q</span><span class="sxs-lookup"><span data-stu-id="a06e4-127">Q\# classifier code</span></span>

<span data-ttu-id="a06e4-128">Agora vamos ver como as operações invocadas pelo programa de acolhimento são definidas em Q# .</span><span class="sxs-lookup"><span data-stu-id="a06e4-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="a06e4-129">Guardamos o seguinte código num ficheiro chamado `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="a06e4-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="a06e4-130">As funções e operações mais importantes definidas no código acima são:</span><span class="sxs-lookup"><span data-stu-id="a06e4-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="a06e4-131">`ClassifierStructure() : ControlledRotation[]` : nesta função definimos a estrutura do nosso modelo de circuito adicionando as camadas dos portões controlados que consideramos.</span><span class="sxs-lookup"><span data-stu-id="a06e4-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="a06e4-132">Este passo é análogo à declaração de camadas de neurónios num modelo sequencial de aprendizagem profunda.</span><span class="sxs-lookup"><span data-stu-id="a06e4-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="a06e4-133">`TrainHalfMoonModel() : (Double[], Double)` : esta operação é a parte central do código e define a formação.</span><span class="sxs-lookup"><span data-stu-id="a06e4-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="a06e4-134">Aqui carregamos as amostras do conjunto de dados incluído na biblioteca, definimos os hipermetrões e os parâmetros iniciais para o treino e começamos a formação chamando a operação `TrainSequentialClassifier` incluída na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a06e4-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="a06e4-135">Produz os parâmetros e o enviesamento que determina o classificador.</span><span class="sxs-lookup"><span data-stu-id="a06e4-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="a06e4-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : esta operação define o processo de validação para avaliar o modelo.</span><span class="sxs-lookup"><span data-stu-id="a06e4-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="a06e4-137">Aqui carregamos as amostras para validação, o número de medições por amostra e a tolerância.</span><span class="sxs-lookup"><span data-stu-id="a06e4-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="a06e4-138">Produz o número de classificações erradas no lote escolhido de amostras para validação.</span><span class="sxs-lookup"><span data-stu-id="a06e4-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a06e4-139">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="a06e4-139">Next steps</span></span>

<span data-ttu-id="a06e4-140">Primeiro, podes jogar com o código e tentar alterar alguns parâmetros para ver como isso afeta o treino.</span><span class="sxs-lookup"><span data-stu-id="a06e4-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="a06e4-141">Em seguida, no próximo tutorial, [desenhe o seu próprio classificador,](xref:microsoft.quantum.libraries.machine-learning.design)aprenderá a definir a estrutura do classificador.</span><span class="sxs-lookup"><span data-stu-id="a06e4-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
