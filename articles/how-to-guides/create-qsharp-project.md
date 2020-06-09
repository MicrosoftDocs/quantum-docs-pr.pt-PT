---
title: Saiba como criar um projeto Q# com o Kit de Desenvolvimento Quântico (QDK)
description: Inicialize um projeto para desenvolvimento quântico com o QDK e Q# no ambiente de desenvolvimento da sua escolha
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578216"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Crie um projeto Q# no seu ambiente de desenvolvimento

Saiba como criar um projeto Q# com o QDK.

Um projeto Q# contém ficheiros Q# que contêm código quântico, bem como um programa de anfitrião para executar o programa quântico. Pode escrever o programa de anfitrião em línguas .NET como C#, ou em Python. Também pode executar o código Q# num Bloco de Notas Jupyter utilizando o núcleo IQ#.

Escolha o seu ambiente de desenvolvimento e linguagem a partir das secções abaixo:

* [Python](#create-a-python-project)
* [Q# Jupyter Notebooks](#create-a-q-jupyter-notebook-project)
* [C# com Visual Studio](#create-a-c-project-on-windows-using-visual-studio)
* [C# com Código VS](#create-a-c-project-using-vs-code)
* [C# com a linha de comando](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Criar um projeto Python

1. Pré-requisitos

     * Instale o [Kit de Desenvolvimento Quântico para Python](xref:microsoft.quantum.install.python)

1. Crie uma pasta para o seu projeto e navegue para essa pasta

1. Crie um ficheiro Q# chamado `Operation.qs` , e adicione o seu código Q# ao mesmo. Por exemplo:

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

1. Crie um ficheiro de hospedeiro python chamado `host.py` para ligar para a sua operação Q#. Por exemplo:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Execute o programa:

    ```
    python host.py
    ```

1. Verifique o resultado. O programa deverá produzir as seguintes linhas:

    ```
    Hello from quantum world!
    0
    ```

Agora pode continuar a desenvolver o seu programa quântico.

## <a name="create-a-q-jupyter-notebook-project"></a>Criar um projeto Q# Jupyter Notebook

1. Pré-requisitos

    * Instale o [Kit de Desenvolvimento Quântico para Cadernos Jupyter](xref:microsoft.quantum.install.jupyter)

1. Execute o comando seguinte para iniciar o servidor de blocos de notas:

    ```
    jupyter notebook
    ```

1. Navegue para o URL mostrado na linha de comandos. Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. Uma página jupyter aparece no navegador. No **separador Ficheiros,** selecione **New**  >  **Q#** para criar um Bloco de Notas Jupyter com um kernel Q# . Adicione o seguinte código à primeira célula do portátil:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Selecione **Cell**  >  **Cell Run Cells** para executar o caderno. `SayHello`em breve aparecerão na saída da célula:

    ![Célula de caderno Jupyter com código Q#](~/media/install-guide-jupyter.png)

    Ao correr em Cadernos Jupyter, o código Q# é compilado e o portátil produz o nome da(s) operação(s) que encontra.

1. Numa nova célula, simule num computador quântico a execução da operação que acabou de criar com o magic `%simulate`:

    ![Célula de Caderno Jupyter com %simular magia](~/media/install-guide-jupyter-simulate.png)

    Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, está vazio).

Agora pode adicionar outras operações Q# para continuar o seu desenvolvimento quântico.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Criar um projeto C# no Windows, utilizando o Visual Studio

1. Pré-requisitos

    * Instale a extensão do [Kit de Desenvolvimento Quântico para o Estúdio Visual](xref:microsoft.quantum.install.cs)

1. Crie uma nova aplicação Q#

    * Ir para **arquivar**  ->  **novo**  ->  **projeto**
    * Escreva `Q#` na caixa de pesquisa
    * Selecione **Aplicação Q#**
    * Selecione **Seguinte**
    * Escolha um nome e uma localização para a aplicação
    * Selecione **Criar**

1. Inspecione o projeto

    Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.

1. Executar a aplicação

    * Selecione **Debug**  ->  **Start Without Debugging**
    * Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.

Agora pode continuar o seu desenvolvimento quântico usando o Visual Studio

> [!NOTE]
> * Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.  

## <a name="create-a-c-project-using-vs-code"></a>Criar um projeto C#, utilizando o Código VS

1. Pré-requisitos

    * Instale a extensão do [Kit de Desenvolvimento Quântico para o Código VS](xref:microsoft.quantum.install.cs)

1. Crie um novo projeto:

    * Ir para **ver paleta**  ->  **de comando**
    * Selecione **Q#: Criar novo projeto**
    * Selecione **aplicação de consola autónoma**
    * Navegue para a localização no sistema de ficheiros onde quer criar a aplicação
    * Clique no botão **Abrir novo projeto...**, após o projeto ser criado.

1. Execute a aplicação:

    * Ir para **terminal**  ->  **novo terminal**
    * Inserir`dotnet run`
    * Deverá ver o seguinte texto na janela de saída `Hello quantum world!`

Agora pode continuar o seu desenvolvimento quântico usando o Código do Estúdio Visual.

> [!NOTE]
> * As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>Criar um projeto C#, utilizando a `dotnet` ferramenta de linha de comando

1. Pré-requisitos

    * Instale o [Kit de Desenvolvimento Quântico para a linha de comando](xref:microsoft.quantum.install.standalone)

1. Criar uma nova aplicação

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. Navegue para o novo diretório de aplicação

    ```
    cd <project name>
    ```

    Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).

1. Executar a aplicação

    ```dotnetcli
    dotnet run
    ```

    Deverá ver o resultado seguinte: `Hello quantum world!`

Agora continuas o teu desenvolvimento quântico, usando ferramentas de linha de comando.

## <a name="next-steps"></a>Próximos passos

Agora que criou um projeto no seu ambiente preferido, pode continuar o seu desenvolvimento quântico.
