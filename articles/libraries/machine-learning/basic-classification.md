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
# <a name="basic-classification-classify-data-with-the-qdk"></a>Classificação básica: Classificar os dados com o QDK

Neste Quickstart, aprenderás a executar um classificador sequencial quântico escrito em Q# utilizando a biblioteca Quantum Machine Learning do QDK. 

Neste guia utilizaremos o conjunto de dados de meia-lua, utilizando uma estrutura de classificador definida em Q#.

## <a name="prerequisites"></a>Pré-requisitos

- O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Crie um projeto Q# para um [programa de anfitrião Python](xref:microsoft.quantum.install.python) ou um programa de [anfitrião C](xref:microsoft.quantum.install.cs)# .

## <a name="host-program"></a>Programa de acolhimento

O seu programa de anfitriões é composto por três partes:

- Carregue o conjunto de dados e escolha um conjunto de parâmetros iniciais para o seu modelo.
- Execute o treino para determinar os parâmetros e o enviesamento do modelo.
- Validar o modelo para determinar a sua precisão

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-python)

    Para executar você é o classificador Q# de Python, guarde o seguinte código como `host.py` . Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Em seguida, pode executar o programa anfitrião do Python na linha de comandos:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-csharp)

    Para executar você é o classificador Q# de C#, guarde o seguinte código como `Host.cs` . Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Em seguida, pode executar o programa anfitrião de C# na linha de comandos:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# com o Visual Studio 2019](#tab/tabid-vs2019)

    Para executar o seu novo programa Q# a partir de C# no Visual Studio, modifique `Host.cs` para incluir o seguinte código C#. Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Em seguida, prima F5, o programa iniciará a execução e será apresentada uma nova janela com os seguintes resultados: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Código \# de classificação Q

Agora vamos ver como as operações invocadas pelo programa anfitrião são definidas em Q#.
Guardamos o seguinte código num ficheiro chamado `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

As funções e operações mais importantes definidas no código acima são:

- `ClassifierStructure() : ControlledRotation[]`: nesta função definimos a estrutura do nosso modelo de circuito adicionando as camadas dos portões controlados que consideramos. Este passo é análogo à declaração de camadas de neurónios num modelo sequencial de aprendizagem profunda.
- `TrainHalfMoonModel() : (Double[], Double)`: esta operação é a parte central do código e define a formação. Aqui carregamos as amostras do conjunto de dados incluído na biblioteca, definimos os hipermetrões e os parâmetros iniciais para o treino e começamos a formação chamando a operação `TrainSequentialClassifier` incluída na biblioteca. Produz os parâmetros e o enviesamento que determina o classificador.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: esta operação define o processo de validação para avaliar o modelo. Aqui carregamos as amostras para validação, o número de medições por amostra e a tolerância. Produz o número de classificações erradas no lote escolhido de amostras para validação.

## <a name="next-steps"></a>Passos seguintes

Primeiro, podes jogar com o código e tentar alterar alguns parâmetros para ver como isso afeta o treino. Em seguida, no próximo tutorial, [desenhe o seu próprio classificador,](xref:microsoft.quantum.libraries.machine-learning.design)aprenderá a definir a estrutura do classificador.
