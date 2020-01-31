---
title: Saiba como atualizar o Kit de Desenvolvimento Quântico da Microsoft (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ed2a90749bbe245dde97424fc3191682f995d85b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819744"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Atualizar o Kit de Desenvolvimento Quântico da Microsoft (QDK)

Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.

Este artigo assume que já tem o QDK instalado. Se estiver a instalar pela primeira vez, consulte o guia de [instalação](xref:microsoft.quantum.install).

Recomendamos que se mantenha atualizado com o mais recente lançamento qDK. Siga este guia de atualização para atualizar para a versão QDK mais recente. O processo consiste em duas partes:
1. atualizando os seus ficheiros e projetos Q# existentes para alinhar o seu código com qualquer sintaxe atualizada
2. atualizando o próprio QDK para o seu ambiente de desenvolvimento escolhido 

## <a name="updating-q-projects"></a>Atualizar projetos Q# 

Independentemente de estar a C# usar ou python para acolher operações q#, siga estas instruções para atualizar os seus projetos Q#.

1. Primeiro, verifique se tem a versão mais recente do [.NET Core SDK 3.1](https://dotnet.microsoft.com/download). Executar o seguinte comando no pedido de comando:
    ```bash
    dotnet --version
    ```
Verifique se a saída é `3.1.100` ou superior. Caso contrário, instale a [versão mais recente](https://dotnet.microsoft.com/download) e verifique novamente. Em seguida, siga as instruções abaixo, dependendo da sua configuração (Visual Studio, Visual Studio Code ou diretamente a linha de comando).

### <a name="update-q-projects-in-visual-studio"></a>Atualizar projetos Q# no Estúdio Visual
 
1. Atualização para a versão mais recente do Visual Studio 2019, consulte [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) as instruções
2. Abra a sua solução no Estúdio Visual
3. No menu, selecione **Build** -> **Clean Solution**
4. Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para `netcoreapp3.0` (ou `netstandard2.1` se for um projeto de biblioteca).
    Ou seja, editar linhas do formulário:
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
5. Guarde e feche todos os ficheiros da sua solução
6. **Selecione ferramentas** -> linha de **comando** -> comando **do desenvolvedor**
7. Para cada projeto na solução, executar o seguinte comando:
    ```bash
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```
    Se os seus projetos utilizarem outros pacotes Microsoft.Quantum (por exemplo, Microsoft.Quantum.Numerics), execute o comando para estes também.
8. Feche o pedido de comando e selecione **Build** -> **Build Solution** *(não* selecione Rebuild Solution, uma vez que a reconstrução falhará inicialmente)

Agora pode saltar para a frente para [atualizar a extensão QDK do Estúdio Visual](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Atualizar projetos Q# no Código do Estúdio Visual

1. No Código do Estúdio Visual, abra a pasta contendo o projeto para atualizar
2. Selecione **terminal** -> **novo terminal**
3. Siga as instruções de atualização utilizando a linha de comando (diretamente abaixo)

### <a name="update-q-projects-using-the-command-line"></a>Atualizar projetos Q# usando a linha de comando

1. Navegue para a pasta que contém o seu ficheiro de projeto
2. Execute o seguinte comando:
    ```bash
    dotnet clean [project_name].csproj
    ```

3. Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para `netcoreapp3.0` (ou `netstandard2.1` se for um projeto de biblioteca).
    Ou seja, editar linhas do formulário:
    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```
    Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
4. Execute o seguinte comando:
    ```bash
    dotnet add package Microsoft.Quantum.Development.Kit
    ```
    Se o seu projeto utilizar outros pacotes Microsoft.Quantum (por exemplo, Microsoft.Quantum.Numerics), execute o comando para estes também.
5. Guarde e feche todos os ficheiros.
6. Repita 1-4 para cada dependência do projeto, depois navegue de volta para a pasta que contém o seu projeto principal e executar:
    ```bash
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
* [Linha de C#comando e : modelos de projeto de atualização](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Atualização IQ# para Python

1. Atualize o núcleo de `iqsharp` 

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifique a versão `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Deverá ver o resultado seguinte:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    Não se preocupe se a sua versão `iqsharp` for maior, deverá corresponder ao [lançamento mais recente](xref:microsoft.quantum.relnotes).

3. Atualizar o pacote `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

4. Verifique a versão `qsharp`

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
5. Execute o seguinte comando a partir da localização dos seus ficheiros `.qs`
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. Agora pode usar a versão QDK atualizada para executar os seus programas quânticos existentes.

### <a name="update-iq-for-jupyter-notebooks"></a>Atualização IQ# para Cadernos Jupyter

1. Atualize o núcleo de `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifique a versão `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    A sua saída deve ser semelhante à seguinte:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```
    Não se preocupe se a sua versão `iqsharp` for maior, deverá corresponder ao [lançamento mais recente](xref:microsoft.quantum.relnotes).

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

   - Aceda a **Ver** -> **Paleta de Comandos**
   - Selecione **Q#: Instale modelos de projeto**
   - Após alguns segundos deve obter um popup confirmando "modelos de projeto instalados com sucesso"

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, utilizando a ferramenta `dotnet` linha de comando

1. Atualizar os modelos de projeto quantum para .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>O que se segue?

Agora que atualizou o Kit de Desenvolvimento Quântico no seu ambiente preferido, pode continuar a desenvolver e executar os seus programas quânticos. Se ainda não escreveu um programa, pode começar com [o seu primeiro programa quântico.](xref:microsoft.quantum.write-program)
