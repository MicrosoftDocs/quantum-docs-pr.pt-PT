---
title: Programar com Q# Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274162"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Programar com Q# Jupyter Notebook

Instale o QDK para desenvolver operações Q# em blocos de notas Q# Jupyter Notebook.

O Jupyter Notebook permitem executar código no local juntamente com instruções, notas e outros conteúdos. Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica. Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.

IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.

> [!NOTE]
> * No Q# Jupyter Notebook, só pode executar código Q# e as operações não podem ser chamadas a partir de programas anfitriões externos (por exemplo, ficheiros Python ou C#). Se o seu objetivo for combinar um programa anfitrião clássico externo com o programa quântico, este ambiente não é o indicado.

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - [Bloco de Notas do Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Instalar o pacote `iqsharp`

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

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Execute o comando seguinte para iniciar o servidor de blocos de notas:

        ```
        jupyter notebook
        ```

    - Para abrir o bloco de notas Jupyter Notebook, copie e cole o URL fornecido pela linha de comandos no browser.

    - Crie um bloco de notas do Jupyter Notebook com um kernel Q# e adicione o seguinte código à primeira célula do bloco de notas:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Execute esta célula do bloco de notas:

        ![Célula do bloco de notas do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

        Deverá ver `SayHello` na saída da célula. Ao executar no Jupyter Notebook, o código Q# é compilado e o bloco de notas produz o nome das operações que encontra.


    - Numa célula nova, execute a operação que acabou de criar (num simulador) com o comando `%simulate`:

        ![Célula do bloco de notas do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

        Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, vemos a cadeia de identificação vazia `()`, porque a operação deve simplesmente um tipo `Unit`).

## <a name="next-steps"></a>Passos seguintes

Agora que instalou o QDK para o Q# Jupyter Notebook, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) ao escrever o código Q# diretamente no ambiente do Jupyter Notebook.

Para obter mais exemplos do que pode fazer com o Q# Jupyter Notebook, veja:
- [Introdução a Q# e ao Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Aqui, encontrará um bloco de notas Q# Jupyter Notebook que mostra como utilizar o Q# neste ambiente.
- [Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção open-source de tutoriais ao seu ritmo e de conjuntos de exercícios de programação na forma de blocos de notas do Q# Jupyter Notebook. Os [blocos de notas de tutoriais do Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida. Os Quantum katas têm como objetivo ensinar-lhe elementos de computação quântica e programação em Q# ao mesmo tempo. São um excelente exemplo dos tipos de conteúdos que pode criar com o Q# Jupyter Notebook.
