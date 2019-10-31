---
title: Saiba como instalar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035285"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalar o Microsoft Quantum Development Kit (QDK)

Saiba como instalar o Microsoft Quantum Development Kit (QDK), para que possa começar a utilizar a programação quântica. O QDK consiste em:

- linguagem de programação Q#
- um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#
- uma aplicação anfitriã (escrita em Python ou uma linguagem .NET) que executa operações quânticas escritas em Q#
- ferramentas para facilitar a programação

Consoante o ambiente de desenvolvimento escolhido, existem diferentes passos de instalação. Escolha o ambiente nas secções seguintes.

## <a name="develop-with-python"></a>Programar com Python

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)
    - SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)

1. Instalar o pacote `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Instalar o pacote `qsharp`

    ```bash
    pip install qsharp
    ```

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Execute o programa:

        ```bash
        python hello_world.py
        ```

    - Verifique o resultado. O programa deverá produzir as seguintes linhas:

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Programar com Jupyter Notebooks

1. Pré-requisitos

    - [Python](https://www.python.org/downloads/) 3.6 ou posterior
    - [Bloco de Notas do Jupyter](https://jupyter.readthedocs.io/en/latest/install.html)
    - SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)

1. Instalar o pacote `iqsharp`

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Execute o comando seguinte para iniciar o servidor de blocos de notas:

        ```bash
        jupyter notebook
        ```

    - Navegue para o URL mostrado na linha de comandos. Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Crie um Jupyter Notebook com um kernel Q# e adicione o seguinte código à primeira célula do bloco de notas:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Execute esta célula do bloco de notas:

        ![Célula do Jupyter Notebook](~/media/install-guide-jupyter.png)

        Deverá ver `SayHello` na saída da célula. Ao executar em Jupyter Notebooks, o código Q# é compilado e o bloco de notas produz o nome das operações que encontra.

## <a name="develop-with-c-on-windows-using-visual-studio"></a>Desenvolver com C# em Windows, com o Visual Studio

1. Pré-requisitos

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, com a carga de trabalho de desenvolvimento para várias plataformas .NET Core ativada

1. Instalar a extensão do Visual Studio Q#

    - Transfira a [extensão do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Adicione a extensão ao Visual Studio

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Crie uma nova aplicação Q#

        - Aceda a **Ficheiro** -> **Novo** -> **Projeto**
        - Escreva `Q#` na caixa de pesquisa
        - Selecione **Aplicação Q#**
        - Selecione **Seguinte**
        - Escolha um nome e uma localização para a aplicação
        - Selecione **Criar**

    - Inspecione o projeto

        Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.

    - Executar a aplicação

        - Selecione **Depurar** -> **Iniciar sem Depurar**
        - Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.

> [!NOTE]
> * Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.  

## <a name="develop-with-c-using-vs-code"></a>Desenvolver com C#, através do VS Code

1. Pré-requisitos

   - [Código VS](https://code.visualstudio.com/download)
   - SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)

1. Instalar a extensão do VS Code Quantum

    - Instale a [extensão do VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Instalar os modelos de projeto Quantum:

   - Aceda a **Ver** -> **Paleta de Comandos**
   - Selecione **Q#: Instalar modelos de projetos**

    Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Crie um novo projeto:

        - Aceda a **Ver** -> **Paleta de Comandos**
        - Selecione **Q#: Criar Novo Projeto**
        - Navegue para a localização no sistema de ficheiros onde quer criar a aplicação
        - Clique no botão **Abrir novo projeto...** , após o projeto ser criado.

    - Execute a aplicação:

        - Aceda a **Depurar** -> **Iniciar sem Depurar**
        - Deverá ver o seguinte texto na janela de saída `Hello quantum world!`

> [!NOTE]
> * > * As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Programar com C# através da ferramenta de linha de comandos `dotnet`

1. Pré-requisitos

    - SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)

1. Instalar os modelos de projeto Quantum para .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Criar uma nova aplicação

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Navegue para o novo diretório de aplicação

       ```bash
       cd runSayHello
       ```

    Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).

    - Executar a aplicação

        ```bash
        dotnet run
        ```

        Deverá ver o resultado seguinte: `Hello quantum world!`

## <a name="whats-next"></a>Passos seguintes?

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).
