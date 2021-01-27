---
title: Programar com Q# e Python
description: Saiba como criar uma aplicação Q# com o Python.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ec40b6f1b7a8d9144860e3b8cfd554eb51bae81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844275"
---
# <a name="develop-with-no-locq-and-python"></a>Programar com Q# e Python

Instale o QDK para desenvolver programas anfitriões Python para chamar operações Q#.

## <a name="install-the-qsharp-python-package"></a>Instale o pacote `qsharp` do Python

### <a name="install-using-conda-recommended"></a>[Instale com o conda (recomendado)](#tab/tabid-conda)

1. Instale o [Miniconda](https://docs.conda.io/en/latest/miniconda.html) ou o [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Nota:** Instalação de 64 bits obrigatória.

1. Abra um Pedido do Anaconda.

   - Em alternativa, se preferir utilizar o PowerShell ou o pwsh:, abra uma shell, execute `conda init powershell`, feche e reabra a shell.

1. Crie e ative um novo ambiente conda com o nome `qsharp-env` com os pacotes necessários (incluindo Jupyter Notebook e IQ#) ao executar os seguintes comandos:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Execute `python -c "import qsharp"` a partir do mesmo terminal para verificar a instalação e povoar a cache de pacotes local com todos os componentes QDK necessários.

### <a name="install-using-net-cli-and-pip-advanced"></a>[Instale com o .NET CLI e o pip (avançado)](#tab/tabid-dotnetcli)

1. Pré-requisitos:

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Instale o pacote `qsharp`, um pacote Python que permite interoperabilidade entre o Q# e o Python.

    ```
    pip install qsharp
    ```

1. Instale o IQ#, um kernel que o Jupyter e o Python utilizam e que proporciona a principal funcionalidade para compilar e executar operações Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Se receber um erro durante o passo `dotnet iqsharp install`, abra uma janela de terminal nova e tente novamente.
    > Se continuar a não funcionar, tente localizar a ferramenta `dotnet-iqsharp` instalada (no Windows, `dotnet-iqsharp.exe`) e executar:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > em que `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta `dotnet-iqsharp` no sistema de ficheiros.
    > Geralmente, estará em `.dotnet/tools` na pasta de perfil de utilizador.
    
**_

Já está! Tem agora o pacote `qsharp` do Python e o kernel do IQ# para Jupyter, que fornecem a principal funcionalidade para compilar e executar operações Q# a partir do Python e utilizar o Q# Jupyter Notebook.

## <a name="choose-your-ide"></a>Escolha o seu IDE

Embora possa utilizar o Q# com o Python em qualquer IDE, recomendamos vivamente utilizar o IDE do Visual Studio Code (VS Code) para as aplicações Q# + Python. Com a extensão QDK do Visual Studio Code, obtém acesso a funcionalidades mais avançadas, como avisos, realce de sintaxe, modelos de projeto e muito mais.

Se quiser utilizar o VS Code:

- Instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
- Instale a [extensão QDK para o VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Se quiser utilizar um editor diferente, as instruções acima têm tudo definido.

## <a name="write-your-first-no-locq-program"></a>Escreva o seu primeiro programa Q#

Agora, está preparado para verificar a instalação do pacote `qsharp` do Python ao escrever e executar um programa Q# simples.

1. Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. Na mesma pasta de `Operation.qs`, crie um programa Python chamado `host.py` para simular a operação Q# `SampleQuantumRandomNumberGenerator()`:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. A partir do ambiente que criou durante a instalação (ou seja, o ambiente conda ou Python onde instalou `qsharp`), execute o programa:

    ```
    python host.py
    ```

1. Deverá ver o resultado da operação que invocou. Neste caso, como a operação gera um resultado aleatório, verá `0` ou `1` impressos no ecrã. Se executar o programa repetidamente, deverá ver cada resultado aproximadamente metade do tempo.

> [!NOTE]
> _ O código Python é apenas um programa python normal. Pode utilizar qualquer ambiente Python, incluindo Jupyter Notebooks baseados em Python, para escrever o programa Python e chamar as operações Q#. O programa Python pode importar operações Q# a partir de quaisquer ficheiros .qs localizados na mesma pasta do próprio código Python.

## <a name="next-steps"></a>Passos seguintes

Agora que testou o Quantum Development Kit no seu ambiente preferido, pode seguir este tutorial para escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
