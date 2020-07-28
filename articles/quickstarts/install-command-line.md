---
title: Programar com aplicações de linha de comandos Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871438"
---
# <a name="develop-with-q-command-line-applications"></a>Programar com aplicações de linha de comandos Q#

Os programas Q# podem ser executados sozinhos, sem um controlador numa linguagem anfitriã, como C#, F# ou Python.

## <a name="prerequisites"></a>Pré-requisitos

- [SDK de .NET Core 3.1 ou versão posterior](https://www.microsoft.com/net/download)

## <a name="installation"></a>Instalação

Embora possa compilar aplicações de linha de comandos Q# em qualquer IDE, recomendamos que utilize o Visual Studio Code (VS Code) ou o Visual Studio IDE para desenvolver as suas aplicações Q# localmente. Para desenvolver na Cloud através do browser, recomendamos o Visual Studio Codespaces. O desenvolvimento nestes ambientes inclui a funcionalidade avançada da extensão QDK, que inclui avisos, realce de sintaxe, modelos de projeto e muito mais. 

Para configurar o VS Code:

1. Transfira e instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
2. Instale o [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Para configurar o Visual Studio:

1. Transfira e instale o [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior com a carga de trabalho de desenvolvimento multiplataforma .NET Core ativada.
2. Transfira e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

Para configurar o Visual Studio Codespaces:

1. Crie uma [conta do Azure](https://azure.microsoft.com/free/).
2. Crie um ambiente do Codespaces. Siga o [guia de início rápido](https://docs.microsoft.com/visualstudio/online/quickstarts/browser). Ao criar o Codespace, recomendamos que introduza `microsoft/Quantum` no campo "Git Repository" (Repositório do Git) para carregar as definições específicas do QDK.
3. Pode agora iniciar o seu novo ambiente e começar a desenvolver no browser através do [IDE da Cloud do VS Codespaces](https://online.visualstudio.com/environments). Pode, em alternativa, utilizar a instalação local do VS Code e utilizar o Codespaces como [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).


Para instalar o QDK para outro ambiente, introduza na linha de comandos:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Programar com Q#

Siga as instruções no separador correspondente ao seu ambiente.

### <a name="vs-code"></a>[Código VS](#tab/tabid-vscode)

Para criar um novo projeto:

1. Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos) e selecione **Q#: Create New Project** (Criar Novo Projeto).
2. Clique em **Standalone console application** (Aplicação de consola autónoma).
3. Navegue para a localização para guardar o projeto e clique em **Create Project** (Criar Projeto).
4. Após a criação do projeto, clique em **Open new project...** (Abrir novo projeto...) no canto inferior direito.
        
Inspecione o projeto. Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.

Para executar a aplicação:
1. Clique em **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).
2. Na mensagem do terminal, introduza `dotnet run`.
3. Deverá ver o seguinte texto na janela de saída `Hello quantum world!`


> [!NOTE]
> As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão Q# do Visual Studio Code. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Crie uma aplicação `Hello World` Q# para verificar a instalação do Visual Studio.

Para criar uma aplicação Q# nova:
1. Abra o Visual Studio e clique em **File** (Ficheiro)  -> **New** (Novo)  -> **Project** (Projeto).
2. Escreva `Q#` na caixa de pesquisa, selecione **Q# Application** (Aplicação Q#) e clique em **Next** (Seguinte).
3. Introduza um nome e uma localização para a aplicação e clique em **Create** (Criar).


Inspecione o projeto. Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.

Para executar a aplicação:
1. Selecione **Debug** (Depurar)  -> **Start Without Debugging** (Iniciar Sem Depuração).
2. Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.

> [!NOTE]
> Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das subpastas.  

### <a name="other-editors-with-the-command-line"></a>[Outros editores com a linha de comandos](#tab/tabid-cmdline)

Crie uma aplicação `Hello World` Q# para verificar a sua instalação.

1. Instale os modelos de projeto.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Crie uma nova aplicação:
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Navegue para o diretório da aplicação:
    ```dotnetcli
    cd runSayHello
    ```

    Este diretório deverá conter um ficheiro `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola. Pode modificar este modelo com um editor de texto e substituí-lo pelas suas próprias aplicações quânticas. 

1. Execute o programa:
    ```dotnetcli
    dotnet run
    ```

1. Deverá ver o seguinte texto impresso: `Hello quantum world!`

***

## <a name="next-steps"></a>Passos seguintes

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
