---
title: 'Saiba como criar um projeto do Q # com o kit de desenvolvimento Quantum (QDK)'
description: 'Inicialize um projeto para o desenvolvimento Quantum com o QDK e o Q # no ambiente de desenvolvimento de sua escolha'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 10b1048501c2de055f5711fc0fdbc4bac76e8f77
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864411"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Criar um projeto do Q # em seu ambiente de desenvolvimento

Saiba como criar um projeto do Q # com o QDK.

Um projeto Q # contém os arquivos Q # contendo o código Quantum, bem como um programa de host para executar o programa Quantum. Você pode escrever o programa host em linguagens C#.net, como ou em Python. Você também pode executar o código Q # em um notebook Jupyter usando o kernel IQ #.

Escolha seu ambiente de desenvolvimento e idioma nas seções a seguir:

* [Python](#create-a-python-project)
* [Blocos de notas do Jupyter](#create-a-jupyter-notebook-project)
* [C#com o Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C#com VS Code](#create-a-c-project-using-vs-code)
* [C#com a linha de comando](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Criar um projeto Python

1. Pré-requisitos

     * O [Kit de desenvolvimento Quantum para Python](xref:microsoft.quantum.install#develop-with-python)

1. Criar uma pasta para seu projeto e navegar até essa pasta

1. Crie um arquivo Q # chamado `Operation.qs`e adicione o código Q # a ele. Por exemplo:

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

1. Crie um arquivo de host Python chamado `host.py` para chamar a operação Q #. Por exemplo:

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

Agora você pode continuar a desenvolver seu programa Quantum.

## <a name="create-a-jupyter-notebook-project"></a>Criar um projeto Jupyter Notebook

1. Pré-requisitos

    * O [Kit de desenvolvimento Quantum para notebooks Jupyter](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)

1. Execute o comando seguinte para iniciar o servidor de blocos de notas:

    ```bash
    jupyter notebook
    ```

1. Navegue para o URL mostrado na linha de comandos. Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Uma página Jupyter aparece no navegador. Na guia **arquivos** , selecione **novo** > **Q #** para criar um notebook Jupyter com um kernel Q #. Adicione o seguinte código à primeira célula do bloco de anotações:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Selecione a **célula** > **executar células** para executar o bloco de anotações. `SayHello` aparecerá em breve na saída da célula:

    ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

    Ao executar em notebooks Jupyter, o código Q # é compilado e o notebook gera o nome da (s) operação (ões) que encontrará.

1. Numa nova célula, simule num computador quântico a execução da operação que acabou de criar com o magic `%simulate`:

    ![Célula do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

    Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, está vazio).

Agora você pode adicionar outras operações Q # para continuar o desenvolvimento do Quantum.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Criar um C# projeto no Windows usando o Visual Studio

1. Pré-requisitos

    * O [Kit de desenvolvimento Quantum para Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)

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

Agora você pode continuar o desenvolvimento do Quantum usando o Visual Studio

> [!NOTE]
> * Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.  

## <a name="create-a-c-project-using-vs-code"></a>Criar um C# projeto, usando vs Code

1. Pré-requisitos

    * O [Kit de desenvolvimento Quantum para vs Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)

1. Crie um novo projeto:

    * Aceda a **Ver** -> **Paleta de Comandos**
    * Selecione **Q #: criar novo projeto**
    * Selecionar **aplicativo de console autônomo**
    * Navegue para a localização no sistema de ficheiros onde quer criar a aplicação
    * Clique no botão **Abrir novo projeto...** , após o projeto ser criado.

1. Execute a aplicação:

    * Ir para **terminal** -> **novo terminal**
    * Inserir `dotnet run`
    * Deverá ver o seguinte texto na janela de saída `Hello quantum world!`

Agora você pode continuar o desenvolvimento do Quantum usando Visual Studio Code.

> [!NOTE]
> * As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Criar um C# projeto, usando a ferramenta de linha de comando `dotnet`

1. Pré-requisitos

    * O [Kit de desenvolvimento Quantum para a linha de comando](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)

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

Agora você continua o desenvolvimento do Quantum, usando as ferramentas de linha de comando.

## <a name="whats-next"></a>O que se segue?

Agora que você criou um projeto em seu ambiente preferido, você pode continuar o desenvolvimento do Quantum.
