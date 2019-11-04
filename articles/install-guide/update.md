---
title: Saiba como atualizar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185856"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Atualizar o Microsoft Quantum Development Kit (QDK)

Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.

Este artigo pressupõe que você já tenha o QDK instalado. Se você estiver instalando o pela primeira vez, consulte o guia de [instalação](xref:microsoft.quantum.install).

As etapas de atualização dependem do ambiente de desenvolvimento. Escolha seu ambiente nas seções a seguir.

## <a name="python"></a>Python

1. Atualizar o kernel `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificar a versão do `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Deverá ver o resultado seguinte:

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Atualizar o pacote de `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

1. Verificar a versão do `qsharp`

    ```bash
    pip show qsharp
    ```

    Deverá ver o resultado seguinte:

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Agora você pode usar a versão atualizada do QDK para executar seus programas de Quantum existentes.

## <a name="jupyter-notebooks"></a>Jupyter Notebooks

1. Atualizar o kernel `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificar a versão do `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Deverá ver o resultado seguinte:

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Agora você pode abrir um bloco de anotações do Jupyter existente e executá-lo com o QDK atualizado.

## <a name="c-on-windows-using-visual-studio"></a>C#no Windows, usando o Visual Studio

1. Atualizar a extensão do Q # Visual Studio

    - O Visual Studio solicita que você aceite atualizações para a [extensão Quantum do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Aceitar a atualização

    > [!NOTE]
    > Os modelos de projeto são atualizados com a extensão. Os modelos atualizados se aplicam apenas a projetos recém-criados. O código para seus projetos existentes não é atualizado quando a extensão é atualizada.

1. Atualizar os pacotes QDK

    - Abrir um aplicativo existente
    - Selecione **dependências** no Gerenciador de soluções
    - Selecione **gerenciar pacotes NuGet**
    - Atualizar os pacotes do **Microsoft. Quantum** para a versão mais recente

1. Agora você pode executar seu aplicativo com o QDK mais recente.

## <a name="c-using-vs-code"></a>C#, usando VS Code

1. Atualizar a extensão de VS Code Quantum

    - Reiniciar VS Code
    - Navegue até a guia **extensões**
    - Selecione o **Microsoft Quantum Development Kit para Visual Studio Code** extensão
    - Recarregar a extensão

1. Atualize os modelos de projeto Quantum:

   - Ir para **exibição** -> **paleta de comandos**
   - Selecione **Q #: instalar modelos de projeto**

1. Abrir um aplicativo existente no VS Code

   - Editar o arquivo. csproj para adicionar as novas versões de pacote

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Se você usar outros pacotes de `Microsoft.Quantum`, atualize-os também.

1. Agora você pode executar seu aplicativo com o QDK atualizado

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, usando a ferramenta de linha de comando `dotnet`

1. Atualizar os modelos de projeto Quantum para .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Atualizar e executar um aplicativo existente

    - Atualizar as versões do pacote QDK em seu aplicativo

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Se seu aplicativo usar qualquer outro pacote de `Microsoft.Quantum`, atualize-o também.

    - Executar a aplicação

        ```bash
        dotnet run
        ```

    - Seu aplicativo será executado com as novas versões de pacote

## <a name="whats-next"></a>O que se segue?

Agora que você atualizou o kit de desenvolvimento Quantum em seu ambiente preferido, você pode continuar a desenvolver e executar seus programas Quantum. Se você ainda não escreveu um programa, você pode começar com [seu primeiro programa Quantum](xref:microsoft.quantum.write-program).
