---
title: Programar com o Q# Jupyter Notebook
description: Saiba como criar uma aplicação Q# com o Jupyter Notebook.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4cef9b7252a2199b2ea995c4cf819a3582d9ca8f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844285"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a>Programar com o Q# Jupyter Notebook

Instale o QDK para desenvolver operações Q# no Q# Jupyter Notebook.

O Jupyter Notebook permitem executar código no local juntamente com instruções, notas e outros conteúdos. Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica. Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.

## <a name="install-the-ino-locq-jupyter-kernel"></a>Instale o kernel do IQ# Jupyter

IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.

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

### <a name="install-using-net-cli-advanced"></a>[Instale com o .NET CLI (avançado)](#tab/tabid-dotnetcli)

1. Pré-requisitos:

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - [Bloco de Notas do Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instale o pacote `Microsoft.Quantum.IQSharp`.

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

Já está! Tem agora o kernel do IQ# para Jupyter, que fornece a principal funcionalidade para compilar e executar operações Q# a partir do Q# Jupyter Notebook.

## <a name="create-your-first-no-locq-notebook"></a>Crie o seu primeiro bloco de notas Q#

Agora, está preparado para verificar a instalação do Q# Jupyter Notebook ao escrever e executar uma operação Q# simples.

1. A partir do ambiente que criou durante a instalação (ou seja, o ambiente conda que criou ou o ambiente Python onde instalou o Jupyter), execute o seguinte comando para iniciar o servidor do Jupyter Notebook:

    ```
    jupyter notebook
    ```

    - Se o Jupyter Notebook não abrir automaticamente no browser, copie e cole o URL fornecido pela linha de comandos no browser.

1. Escolha _ *Nova → Q#** para criar um Caderno Jupyter com um Q# núcleo e adicione o seguinte código à primeira célula do portátil:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Execute esta célula do bloco de notas:

    ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

    Deverá ver `SampleQuantumRandomNumberGenerator` na saída da célula. Ao executar no Jupyter Notebook, o código Q# é compilado e a célula produz o nome das operações que encontra.

1. Numa célula nova, execute a operação que acabou de criar (num simulador) com o comando `%simulate`:

    ![Célula do bloco de notas do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

    Deverá ver o resultado da operação que invocou. Neste caso, como a operação gera um resultado aleatório, verá `Zero` ou `One` impressos no ecrã. Se executar a célula repetidamente, deverá ver cada resultado aproximadamente metade do tempo.

## <a name="next-steps"></a>Passos seguintes

Agora que instalou o QDK para o Q# Jupyter Notebook, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) ao escrever código Q# diretamente no ambiente do Jupyter Notebook.

Para obter mais exemplos do que pode fazer com o Q# Jupyter Notebook, veja:

- [Introdução ao Q# e ao Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Aqui, encontrará um Q# Jupyter Notebook que mostra mais detalhes sobre como utilizar o Q# no ambiente do Jupyter.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção open-source de tutoriais ao seu ritmo e de conjuntos de exercícios de programação na forma de blocos de notas do Q# Jupyter Notebook. Os [blocos de notas de tutoriais do Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida. Os Quantum Katas têm como objetivo ensinar-lhe elementos de computação quântica e programação em Q# ao mesmo tempo. São um excelente exemplo dos tipos de conteúdos que pode criar com o Q# Jupyter Notebook.
