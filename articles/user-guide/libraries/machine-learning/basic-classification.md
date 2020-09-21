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
# <a name="basic-classification-classify-data-with-the-qdk"></a>Classificação básica: Classificar os dados com o QDK

Neste Quickstart, você aprenderá a executar um classificador sequencial quântico escrito na Q# utilização da biblioteca Quantum Machine Learning do QDK. 

Neste guia utilizaremos o conjunto de dados de meia-lua, utilizando uma estrutura de classificador definida em Q# .

## <a name="prerequisites"></a>Pré-requisitos

- O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Crie um Q# projeto para um programa de [anfitrião Python](xref:microsoft.quantum.install.python) ou um programa de [anfitrião C#](xref:microsoft.quantum.install.cs).

## <a name="host-program"></a>Programa de acolhimento

O seu programa de anfitriões é composto por três partes:

- Carregue o conjunto de dados e escolha um conjunto de parâmetros iniciais para o seu modelo.
- Executar treino para determinar os parâmetros e o enviesamento do modelo.
- Validar o modelo para determinar a sua precisão

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-python)

    Para executar você é o Q# classificador de Python, guarde o seguinte código como `host.py` . Lembre-se que também precisa do Q# ficheiro que é explicado mais tarde neste `Training.qs` tutorial.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Em seguida, pode executar o programa anfitrião do Python na linha de comandos:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-csharp)

    Para executar você é o Q# classificador de C#, guarde o seguinte código como `Host.cs` . Lembre-se que também precisa do Q# ficheiro que é explicado mais tarde neste `Training.qs` tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Em seguida, pode executar o programa anfitrião de C# na linha de comandos:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# com o Visual Studio 2019](#tab/tabid-vs2019)

    Para executar o seu novo Q# programa a partir de C# no Visual Studio, modifique para incluir o seguinte código `Host.cs` C#. Lembre-se que também precisa do Q# ficheiro que é explicado mais tarde neste `Training.qs` tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Prima F5 e o programa começará a funcionar. Uma nova janela apresentará os seguintes resultados: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Código \# de classificação Q

Agora vamos ver como as operações invocadas pelo programa de acolhimento são definidas em Q# .
Guardamos o seguinte código num ficheiro chamado `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

As funções e operações mais importantes definidas no código acima são:

- `ClassifierStructure() : ControlledRotation[]` : nesta função definimos a estrutura do nosso modelo de circuito adicionando as camadas dos portões controlados que consideramos. Este passo é análogo à declaração de camadas de neurónios num modelo sequencial de aprendizagem profunda.
- `TrainHalfMoonModel() : (Double[], Double)` : esta operação é a parte central do código e define a formação. Aqui carregamos as amostras do conjunto de dados incluído na biblioteca, definimos os hipermetrões e os parâmetros iniciais para o treino e começamos a formação chamando a operação `TrainSequentialClassifier` incluída na biblioteca. Produz os parâmetros e o enviesamento que determina o classificador.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : esta operação define o processo de validação para avaliar o modelo. Aqui carregamos as amostras para validação, o número de medições por amostra e a tolerância. Produz o número de classificações erradas no lote escolhido de amostras para validação.

## <a name="next-steps"></a>Passos seguintes

Primeiro, podes jogar com o código e tentar alterar alguns parâmetros para ver como isso afeta o treino. Em seguida, no próximo tutorial, [desenhe o seu próprio classificador,](xref:microsoft.quantum.libraries.machine-learning.design)aprenderá a definir a estrutura do classificador.
