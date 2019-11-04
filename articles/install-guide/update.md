---
title: Saiba como atualizar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463292"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Atualizar o Microsoft Quantum Development Kit (QDK)

Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.

Este artigo pressupõe que você já tenha o QDK instalado. Se você estiver instalando o pela primeira vez, consulte o guia de [instalação](xref:microsoft.quantum.install).


## <a name="updating-q-projects"></a>Atualizando projetos de Q # 

1. Primeiro, instale a versão mais recente do [SDK do .NET Core 3,0](https://dotnet.microsoft.com/download) e execute o seguinte comando no prompt de comando:
```bash
dotnet --version
```
 Verifique se a saída é 3.0.100 ou superior e siga as instruções abaixo, dependendo da sua configuração.

### <a name="in-visual-studio"></a>No Visual Studio
 
 1. Atualize para a versão mais recente do Visual Studio 2019, consulte [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obter instruções
 2. Abra sua solução no Visual Studio
 3. No menu, selecione criar > solução de limpeza 
 4. [Atualize a estrutura de destino](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) em cada um dos seus arquivos. csproj para o netcoreapp 3.0 (ou o netstandard 2.1 se for um projeto de biblioteca)
 5. Salvar e fechar todos os arquivos em sua solução
 6. Selecione Ferramentas > > de linha de comando Prompt de Comando do Desenvolvedor
 7. Para cada projeto na solução, execute o seguinte comando:
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Se seus projetos usarem outros pacotes do Microsoft. Quantum, execute o comando para eles também. 
 8. Feche o prompt de comando e selecione Compilar > Compilar solução ( *não selecione* recompilar solução, pois a recompilação falhará inicialmente)

### <a name="in-visual-studio-code"></a>Em Visual Studio Code

1. Em Visual Studio Code, abra a pasta que contém o projeto a ser atualizado
1. Selecionar Terminal > novo terminal
1. Siga as instruções para atualizar usando a linha de comando

### <a name="using-the-command-line"></a>Usando a linha de comando

1. Navegue até a pasta que contém o arquivo de projeto
2. Execute o seguinte comando:
```bash
dotnet clean [project_name].csproj
```

3. [Atualize a estrutura de destino](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) em cada um dos seus arquivos. csproj para o netcoreapp 3.0 (ou o netstandard 2.1 se for um projeto de biblioteca)
4. Execute o seguinte comando:
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
Se seu projeto usar qualquer outro pacote do Microsoft. Quantum, execute o comando para eles também.

5. Salvar e fechar todos os arquivos
6. Repita a 1-4 para cada dependência do projeto e, em seguida, navegue de volta para a pasta que contém o projeto principal e execute:
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Atualizar IQ # para Python

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
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
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
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. Execute o seguinte comando no local de seus arquivos de `.qs`
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. Agora você pode usar a versão atualizada do QDK para executar seus programas de Quantum existentes.

## <a name="update-iq-for-jupyter-notebooks"></a>Atualizar IQ # para notebooks Jupyter

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
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Execute o seguinte comando de uma célula no seu Jupyter Notebook:
    ```
    %workspace reload
    ```

1. Agora você pode abrir um bloco de anotações do Jupyter existente e executá-lo com o QDK atualizado.

## <a name="update-visual-studio-qdk-extension"></a>Atualizar a extensão QDK do Visual Studio

1. Atualizar a extensão do Q # Visual Studio

    - O Visual Studio solicita que você aceite atualizações para a [extensão Quantum do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Aceitar a atualização

    > [!NOTE]
    > Os modelos de projeto são atualizados com a extensão. Os modelos atualizados se aplicam apenas a projetos recém-criados. O código para seus projetos existentes não é atualizado quando a extensão é atualizada.

## <a name="update-vs-code-qdk-extension"></a>Atualizar VS Code extensão QDK

1. Atualizar a extensão de VS Code Quantum

    - Reiniciar VS Code
    - Navegue até a guia **extensões**
    - Selecione o **Microsoft Quantum Development Kit para Visual Studio Code** extensão
    - Recarregar a extensão

1. Atualize os modelos de projeto Quantum:

   - Aceda a **Ver** -> **Paleta de Comandos**
   - Selecione **Q #: instalar modelos de projeto**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, usando a ferramenta de linha de comando `dotnet`

1. Atualizar os modelos de projeto Quantum para .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>O que se segue?

Agora que você atualizou o kit de desenvolvimento Quantum em seu ambiente preferido, você pode continuar a desenvolver e executar seus programas Quantum. Se você ainda não escreveu um programa, você pode começar com [seu primeiro programa Quantum](xref:microsoft.quantum.write-program).
