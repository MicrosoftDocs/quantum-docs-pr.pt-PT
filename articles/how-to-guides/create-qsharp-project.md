---
title: Saiba como criar um projeto Q# com o Quantum Development Kit (QDK)
description: Inicialize um projeto para o desenvolvimento quântico com o QDK e Q# no ambiente de desenvolvimento da sua escolha
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 5fa32f14291fa2070b49e4bb3b720cbf31ee614b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819897"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Crie um projeto Q# no seu ambiente de desenvolvimento

Aprenda a criar um projeto Q# com o QDK.

Um projeto Q# contém ficheiros Q# contendo código quântico, bem como um programa de anfitriões para executar o programa quântico. Pode escrever o programa anfitrião em C#línguas .NET, como, ou em Python. Você também pode executar o código Q# em um caderno Jupyter usando o kernel IQ#.

Escolha o seu ambiente e linguagem de desenvolvimento nas secções abaixo:

* [Python](#create-a-python-project)
* [Cadernos Q# Jupyter](#create-a-q-jupyter-notebook-project)
* [C#com Estúdio Visual](#create-a-c-project-on-windows-using-visual-studio)
* [C#com código VS](#create-a-c-project-using-vs-code)
* [C#com a linha de comando](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Criar um projeto Python

1. Pré-requisitos

     * Instale o [Kit de Desenvolvimento Quântico para Python](xref:microsoft.quantum.install.python)

1. Crie uma pasta para o seu projeto e navegue para essa pasta

1. Crie um ficheiro Q# chamado `Operation.qs`e adicione-lhe o seu código Q#. Por exemplo:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Crie um ficheiro de anfitriões python chamado `host.py` para ligar para a sua operação Q#. Por exemplo:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Execute o programa:

    ```bash
    python host.py
    ```

1. Verifique o resultado. O programa deverá produzir as seguintes linhas:

    ```bash
    Hello from quantum world!
    0
    ```

Agora pode continuar a desenvolver o seu programa quântico.

## <a name="create-a-q-jupyter-notebook-project"></a>Crie um projeto Q# Jupyter Notebook

1. Pré-requisitos

    * Instale o [Kit de Desenvolvimento Quântico para os cadernos Jupyter](xref:microsoft.quantum.install.jupyter)

1. Execute o comando seguinte para iniciar o servidor de blocos de notas:

    ```bash
    jupyter notebook
    ```

1. Navegue para o URL mostrado na linha de comandos. Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Uma página de Jupyter aparece no navegador. No separador **Ficheiros,** selecione **New** > **Q#** para criar um caderno Jupyter com um kernel Q#. Adicione o seguinte código à primeira célula de caderno:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Selecione **Cell** > **Executar Células** para executar o caderno. `SayHello` aparecerão em breve na saída da célula:

    ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

    Ao ser recorrido em Cadernos Jupyter, o código Q# é compilado e o caderno produz o nome da operação(s) que encontra.

1. Numa nova célula, simule num computador quântico a execução da operação que acabou de criar com o magic `%simulate`:

    ![Célula do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

    Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, está vazio).

Agora pode adicionar outras operações de Q# para continuar o seu desenvolvimento quântico.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Criar C# um projeto no Windows, utilizando o Visual Studio

1. Pré-requisitos

    * Instale a [extensão do Kit de Desenvolvimento Quântico para Estúdio Visual](xref:microsoft.quantum.install.cs)

1. Crie uma nova aplicação Q#

    * Aceda a **Ficheiro** -> **Novo** -> **Projeto**
    * Escreva `Q#` na caixa de pesquisa
    * Selecione **Aplicação Q#**
    * Selecione **Seguinte**
    * Escolha um nome e uma localização para a aplicação
    * Selecione **Criar**

1. Inspecione o projeto

    Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.

1. Executar a aplicação

    * Selecione **Depurar** -> **Iniciar sem Depurar**
    * Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.

Agora pode continuar o seu desenvolvimento quântico usando o Visual Studio

> [!NOTE]
> * Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.  

## <a name="create-a-c-project-using-vs-code"></a>Criar C# um projeto, usando o Código VS

1. Pré-requisitos

    * Instale a [extensão do Kit de Desenvolvimento Quântico para o Código VS](xref:microsoft.quantum.install.cs)

1. Crie um novo projeto:

    * Aceda a **Ver** -> **Paleta de Comandos**
    * Selecione **Q#: Criar novo projeto**
    * Selecione **aplicação** de consola autónoma
    * Navegue para a localização no sistema de ficheiros onde quer criar a aplicação
    * Clique no botão **Abrir novo projeto...** , após o projeto ser criado.

1. Execute a aplicação:

    * Ir ao **Terminal** -> **Novo Terminal**
    * Insira `dotnet run`
    * Deverá ver o seguinte texto na janela de saída `Hello quantum world!`

Agora pode continuar o seu desenvolvimento quântico usando o Visual Studio Code.

> [!NOTE]
> * As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Criar C# um projeto, utilizando a ferramenta `dotnet` linha de comando

1. Pré-requisitos

    * Instale o [Kit de Desenvolvimento Quântico para a Linha de Comando](xref:microsoft.quantum.install.cs)

1. Criar uma nova aplicação

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Navegue para o novo diretório de aplicação

    ```bash
    cd <project name>
    ```

    Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).

1. Executar a aplicação

    ```bash
    dotnet run
    ```

    Deverá ver o resultado seguinte: `Hello quantum world!`

Agora continua o teu desenvolvimento quântico, usando ferramentas de linha de comando.

## <a name="whats-next"></a>O que se segue?

Agora que criou um projeto no seu ambiente preferido, pode continuar o seu desenvolvimento quântico.
