---
title: Classificação básica com a biblioteca quantum machine learning
description: Aprenda a executar um classificador sequencial quântico escrito em Q# usando a biblioteca Quantum Machine Learning do Microsoft QDK.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: f42e3e4492f934d7a8f03d4fec6fa0de765401d7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909930"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Classificação básica: Classificar os dados com o QDK

Neste Quickstart, aprenderás a executar um classificador sequencial quântico escrito em Q# usando a biblioteca quantum machine learning do QDK. 

Neste guia usaremos o conjunto de dados de meia-lua, utilizando uma estrutura de classificação definida em Q#.

## <a name="prerequisites"></a>Pré-requisitos

- O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Criar um Projeto Q#](xref:microsoft.quantum.howto.createproject)

## <a name="host-program"></a>Programa de anfitriões

O seu programa de anfitriões é composto por três partes:

- Carregue o conjunto de dados e escolha um conjunto de parâmetros de arranque para o seu modelo.
- Execute o treino para determinar os parâmetros e o enviesamento do modelo.
- Validar o modelo para determinar a sua precisão

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-python)

    Para correr você é o classificador Q# de Python, guarde o seguinte código como `host.py`. Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Em seguida, pode executar o programa anfitrião do Python na linha de comandos:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# com o Visual Studio Code ou a Linha de Comandos](#tab/tabid-csharp)

    Para correr você é o classificador C#Q# de , guarde o seguinte código como `Host.cs`. Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Em seguida, pode executar o programa anfitrião de C# na linha de comandos:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# com o Visual Studio 2019](#tab/tabid-vs2019)

    Para executar o seu C# novo programa Q# a partir C# do Estúdio Visual, modifique `Host.cs` para incluir o seguinte código. Lembre-se que também precisa do ficheiro Q# `Training.qs` que é explicado mais tarde neste tutorial.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Em seguida, prima F5, o programa iniciará a execução e será apresentada uma nova janela com os seguintes resultados: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q código de classificação\#

Agora vamos ver como as operações invocadas pelo programa anfitrião são definidas em Q#.
Guardamos o seguinte código num ficheiro chamado `Training.qs`.

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

As funções e operações mais importantes definidas no código acima são:

- `ClassifierStructure() : ControlledRotation[]`: nesta função definimos a estrutura do nosso modelo de circuito adicionando as camadas dos portões controlados que consideramos. Este passo é análogo à declaração de camadas de neurónios num modelo sequencial de aprendizagem profunda.
- `TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: esta operação é a parte central do código e define a formação. Aqui carregamos as amostras do conjunto de dados incluídona biblioteca, definimos os parâmetros hipere os parâmetros iniciais para o treino e começamos o treino chamando a operação `TrainSequentialClassifier` incluída na biblioteca. Produz os parâmetros e o enviesamento que determinam o classificador.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : esta operação define o processo de validação para avaliar o modelo. Aqui carregamos as amostras para validação, o número de medições por amostra e a tolerância. Produz o número de classificações erradas no lote escolhido de amostras para validação.

## <a name="next-steps"></a>Passos seguintes

Primeiro, pode sondar com o código e tentar alterar alguns parâmetros para ver como afeta o treino. Depois, no próximo tutorial, [Desenhe o seu próprio classificador,](xref:microsoft.quantum.libraries.machine-learning.design)aprenderá a definir a estrutura do classificador.
