---
title: Atualizar o Kit de Desenvolvimento Quântico (QDK)
description: Descreve como atualizar os seus projetos Q# e o Microsoft Quantum Development Kit para a versão atual.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 53f72f1d49ae32a5a8572a1cf68a66a1d9b45e4a
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426914"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Atualizar o Kit de Desenvolvimento Quântico da Microsoft (QDK)

Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.

Este artigo assume que já tem o QDK instalado. Se estiver a instalar pela primeira vez, consulte o guia de [instalação](xref:microsoft.quantum.install).

Recomendamos que se mantenha atualizado com o mais recente lançamento qDK. Siga este guia de atualização para atualizar para a versão QDK mais recente. O processo consiste em duas partes:
1. atualizando os seus ficheiros e projetos Q# existentes para alinhar o seu código com qualquer sintaxe atualizada
2. atualizando o próprio QDK para o seu ambiente de desenvolvimento escolhido 

## <a name="updating-q-projects"></a>Atualizar projetos Q# 

Independentemente de estar a usar c# ou Python para acolher operações q#, siga estas instruções para atualizar os seus projetos Q#.

1. Primeiro, verifique se tem a versão mais recente do [.NET Core SDK 3.1](https://dotnet.microsoft.com/download). Executar o seguinte comando no pedido de comando:

    ```dotnetcli
    dotnet --version
    ```

    Verifique se a saída é `3.1.100` ou superior. Caso contrário, instale a [versão mais recente](https://dotnet.microsoft.com/download) e verifique novamente. Em seguida, siga as instruções abaixo, dependendo da sua configuração (Visual Studio, Visual Studio Code ou diretamente a linha de comando).

### <a name="update-q-projects-in-visual-studio"></a>Atualizar projetos Q# no Estúdio Visual
 
1. Atualização para a versão mais recente do Visual Studio 2019, consulte [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) as instruções
2. Abra a sua solução no Estúdio Visual
3. A partir do menu, selecione **Build**  ->  **Clean Solution**
4. Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para (ou se for um projeto de `netcoreapp3.1` `netstandard2.1` biblioteca).
    Ou seja, editar linhas do formulário:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
5. Guarde e feche todos os ficheiros da sua solução
6. Selecione **ferramentas**Comando de  ->  **linha**  ->  **de comando aviso de comando**
7. Para cada projeto na solução, executar o seguinte comando:

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Se os seus projetos utilizarem outros pacotes Microsoft.Quantum (por exemplo, Microsoft.Quantum.Numerics), execute o comando para estes também.
8. Feche o pedido de comando e selecione **Build**  ->  **Build Solution** *(não* selecione Rebuild Solution)

Agora pode saltar para a frente para [atualizar a extensão QDK do Estúdio Visual](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Atualizar projetos Q# no Código do Estúdio Visual

1. No Código do Estúdio Visual, abra a pasta contendo o projeto para atualizar
2. Selecione **Terminal**  ->  **terminal novo terminal novo**
3. Siga as instruções de atualização utilizando a linha de comando (diretamente abaixo)

### <a name="update-q-projects-using-the-command-line"></a>Atualizar projetos Q# usando a linha de comando

1. Navegue para a pasta que contém o seu ficheiro de projeto
2. Execute o seguinte comando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para (ou se for um projeto de `netcoreapp3.1` `netstandard2.1` biblioteca).
    Ou seja, editar linhas do formulário:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
4. Execute o seguinte comando:

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    Se o seu projeto utilizar outros pacotes Microsoft.Quantum (por exemplo, Microsoft.Quantum.Numerics), execute o comando para estes também.
5. Guarde e feche todos os ficheiros.
6. Repita 1-4 para cada dependência do projeto, depois navegue de volta para a pasta que contém o seu projeto principal e executar:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Com os seus projetos Q# agora atualizados, siga as instruções abaixo para atualizar o próprio QDK.

## <a name="updating-the-qdk"></a>Atualizar o QDK

O processo de atualização do QDK varia consoante a sua linguagem e ambiente de desenvolvimento.
Selecione o seu ambiente de desenvolvimento abaixo.

* [Python: atualizar a extensão IQ#](#update-iq-for-python)
* [Cadernos Jupyter: atualizar a extensão IQ#](#update-iq-for-jupyter-notebooks)
* [Estúdio Visual: atualizar a extensão QDK](#update-visual-studio-qdk-extension)
* [Código VS: atualizar a extensão QDK](#update-vs-code-qdk-extension)
* [Linha de comando e C#: modelos de projeto de atualização](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Atualização IQ# para Python

1. Atualizar o `iqsharp` núcleo 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifique a `iqsharp` versão

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Deverá ver o resultado seguinte:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Não se preocupe se a sua `iqsharp` versão for mais alta, deverá corresponder ao [lançamento mais recente](xref:microsoft.quantum.relnotes).

3. Atualizar o `qsharp` pacote

    ```bash
    pip install qsharp --upgrade
    ```

4. Verifique a `qsharp` versão

    ```bash
    pip show qsharp
    ```

    Deverá ver o resultado seguinte:

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Executar o seguinte comando a partir da localização dos seus `.qs` ficheiros

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Agora pode usar a versão QDK atualizada para executar os seus programas quânticos existentes.

### <a name="update-iq-for-jupyter-notebooks"></a>Atualização IQ# para Cadernos Jupyter

1. Atualizar o `iqsharp` núcleo

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifique a `iqsharp` versão

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A sua saída deve ser semelhante à seguinte:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Não se preocupe se a sua `iqsharp` versão for mais alta, deverá corresponder ao [lançamento mais recente](xref:microsoft.quantum.relnotes).

3. Execute o seguinte comando a partir de uma célula no seu Caderno Jupyter:

    ```
    %workspace reload
    ```

4. Agora pode abrir um caderno Jupyter existente e executá-lo com o QDK atualizado.

### <a name="update-visual-studio-qdk-extension"></a>Atualizar extensão QDK do Estúdio Visual

1. Atualizar a extensão q# Estúdio Visual

    - Visual Studio pede-lhe para aceitar atualizações para a [extensão do Quantum Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Aceite a atualização

    > [!NOTE]
    > Os modelos do projeto são atualizados com a extensão. Os modelos atualizados aplicam-se apenas a projetos recém-criados. O código para os seus projetos existentes não é atualizado quando a extensão é atualizada.

### <a name="update-vs-code-qdk-extension"></a>Atualizar extensão qDK código VS

1. Atualizar a extensão do Código Vs Quântico

    - Reiniciar código VS
    - Navegue para o separador **Extensões**
    - Selecione o Kit de **Desenvolvimento Quântico da Microsoft para** extensão do Código do Estúdio Visual
    - Recarregar a extensão

2. Atualizar os modelos do projeto Quantum:

   - Ir **ver**paleta de  ->  **comando**
   - Selecione **Q#: Instale modelos de projeto**
   - Após alguns segundos deve obter um popup confirmando "modelos de projeto instalados com sucesso"

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, usando a `dotnet` ferramenta de linha de comando

1. Atualizar os modelos de projeto quantum para .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```