---
title: Desenvolver com Q# +C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036292"
---
# <a name="develop-with-q--c"></a>Desenvolver com Q# +C#

Instale o QDK para desenvolver C# programas de anfitriões para ligar para as operações Q#.

Q# é construído para brincar bem com C#.NET idiomas -- especificamente . Você pode trabalhar com este emparelhamento dentro de diferentes ambientes de desenvolvimento:

- [Q# C# + usando o Estúdio Visual (Windows)](#VS)
- [Q# C# + usando código de estúdio visual (Windows, Linux e Mac)](#VSC)
- [Q # C# + usando a ferramenta de linha de comando `dotnet`](#command)

## Desenvolver com Q# + C# usando o Visual Studio <a name="VS"></a>

O Visual Studio oferece um ambiente rico para desenvolver programas Q#. A extensão Q# Visual Studio contém modelos para ficheiros e projetos Q# bem como realce de sintaxe, conclusão de código e suporte intelliSense.


1. Pré-requisitos

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, com a carga de trabalho de desenvolvimento para várias plataformas .NET Core ativada

1. Instalar a extensão do Visual Studio Q#

    - Descarregue e instale a [extensão do Estúdio Visual](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

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

## Desenvolver com Q# + C# usando código de estúdio visual <a name="VSC"></a>

O Visual Studio Code (VS Code) oferece um ambiente rico para desenvolver programas Q# no Windows, Linux e Mac.  A extensão do Código Q# VS inclui suporte para destaque de sintaxe Q#, conclusão de código e snippets de código Q#

1. Pré-requisitos

   - [Código VS](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.1 ou posterior](https://www.microsoft.com/net/download)

1. Instalar a extensão do VS Code Quantum

    - Instale a [extensão do VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Instalar os modelos de projeto Quantum:

   - Aceda a **Ver** -> **Paleta de Comandos**
   - Selecione **Q#: Instale modelos de projeto**

    Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Crie um novo projeto:

        - Aceda a **Ver** -> **Paleta de Comandos**
        - Selecione **Q#: Criar novo projeto**
        - Selecione **aplicação** de consola autónoma
        - Navegue para a localização no sistema de ficheiros onde quer criar a aplicação
        - Clique no botão **Abrir novo projeto...** , após o projeto ser criado.

    - Se ainda não tiver C# a extensão do Código VS instalada, aparecerá um pop-up. Instale a extensão. 

    - Execute a aplicação:

        - Ir ao **Terminal** -> **Novo Terminal**
        - Insira `dotnet run`
        - Deverá ver o seguinte texto na janela de saída `Hello quantum world!`


> [!NOTE]
> * As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code. Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.

## Desenvolver com Q# + C# utilizando a ferramenta de linha de comando `dotnet`<a name="command"></a>

Como é óbvio, também pode criar e executar programas Q# a partir da linha de comandos ao simplesmente instalar o SDK de .NET Core e os modelos de projeto do QDK. 

1. Pré-requisitos

    - [.NET Core SDK 3.1 ou posterior](https://www.microsoft.com/net/download)

1. Instalar os modelos de projeto Quantum para .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.

1. Verificar a instalação ao criar uma aplicação `Hello World`

    - Criar uma nova aplicação

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - Navegue para o novo diretório de aplicação

       ```bash
       cd runSayHello
       ```

    Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).

    - Executar a aplicação

        ```dotnetcli
        dotnet run
        ```

        Deverá ver o resultado seguinte: `Hello quantum world!`

    
## <a name="whats-next"></a>Passos seguintes?

Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).
