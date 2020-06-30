---
title: Atualizar o Quantum Development Kit (QDK)
description: Descreve como atualizar os projetos Q# e o Microsoft Quantum Development kit para a versão atual.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274141"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Atualizar o Microsoft Quantum Development kit (QDK)

Saiba como atualizar o Microsoft Quantum Development kit (QDK) para a versão mais recente.

Este artigo pressupõe que já tem o QDK instalado. Se estiver a instalar pela primeira vez, veja o [guia de instalação](xref:microsoft.quantum.install).

Recomendamos utilizar a última versão do QDK. Para atualizar para a versão mais recente do QDK, siga este guia de atualização. O processo consiste em duas partes:
1. Atualizar os ficheiros e projetos Q# já existentes para alinhar o código com eventuais sintaxes atualizadas.
2. Atualizar o QDK propriamente dito para o ambiente de desenvolvimento que escolheu.

## <a name="updating-q-projects"></a>Atualizar os Projetos Q# 

Independentemente de utilizar C# ou Python para alojar operações Q#, siga estas instruções para atualizar os seus projetos Q#.

1. Primeiro, verifique se tem a última versão do [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download). Execute o seguinte comando na linha de comandos:

    ```dotnetcli
    dotnet --version
    ```

    Veja se a saída é `3.1.100` ou superior. Se não for, instale a [versão mais recente](https://dotnet.microsoft.com/download) e verifique novamente. Depois, consoante a sua configuração (Visual Studio, Visual Studio Code ou a linha de comandos diretamente), siga as instruções abaixo.

### <a name="update-q-projects-in-visual-studio"></a>Atualizar projetos Q# no Visual Studio
 
1. Atualize para a versão mais recente do Visual Studio 2019; veja as instruções [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).
2. Abra a sua solução no Visual Studio.
3. No menu, selecione **Build** (Compilar)  -> **Clean Solution** (Limpar Solução).
4. Em cada ficheiro .csproj, atualize o framework de destino para `netcoreapp3.1` (ou `netstandard2.1`, se for um projeto de biblioteca).
    Ou seja, edite as linhas do formulário:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Pode obter mais detalhes sobre como especificar os frameworks de destino [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. Em cada ficheiro .csproj, defina o SDK com `Microsoft.Quantum.Sdk`, conforme indicado na linha abaixo. Tenha em conta que o número da versão deve ser o último disponível. Para saber qual é, reveja as [notas de versão](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Guarde e feche todos os ficheiros da solução.

7. Selecione **Tools** (Ferramentas)  -> **Command Line** (Linha de Comandos)  -> **Developer Command Prompt** (Linha de Comandos de Programador). Em alternativa, pode utilizar a consola do gestor de pacotes no Visual Studio.

8. Em cada projeto na solução, execute o comando seguinte para **remover** este pacote:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Se os seus projetos utilizarem quaisquer outros pacotes do Microsoft.Quantum ou do Microsoft.Azure.Quantum packages (por exemplo, Microsoft.Quantum.Numerics), execute o comando **add** para os mesmos, de modo a atualizar a versão utilizada.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Escolha a linha de comandos e selecione **Build** (Compilar)  -> **Build Solution** (Compilar Solução) (*não* selecione Rebuild Solution [Recompilar Solução]).

Agora, pode avançar para a [atualização da extensão QDK do Visual Studio](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Atualizar projetos Q# no Visual Studio Code

1. No Visual Studio Code, abra a pasta que contém o projeto a atualizar.
2. Selecione **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).
3. Siga as instruções de atualização com a linha de comandos (diretamente abaixo).

### <a name="update-q-projects-using-the-command-line"></a>Atualizar projetos Q# com a linha de comandos

1. Navegue para a pasta que contém o ficheiro de projeto principal.

2. Execute o seguinte comando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Determine a versão atual do QDK. Para isso, reveja as [notas de versão](https://docs.microsoft.com/quantum/relnotes/). A versão estará num formato semelhante a `0.11.2006.207`.

4. Em cada ficheiro `.csproj`, percorra os passos abaixo:

    - Atualize o framework de destino para `netcoreapp3.1` (ou `netstandard2.1`, se for um projeto de biblioteca). Ou seja, edite as linhas do formulário:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Pode obter mais detalhes sobre como especificar os frameworks de destino [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Substitua a referência ao SDK na definição do projeto. Confirme que o número da versão corresponde ao valor determinado no **passo 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Se presente, remova a referência ao pacote `Microsoft.Quantum.Development.Kit`, que será especificada na seguinte entrada:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Atualize a versão de todos os pacotes do Microsoft Quantum para a mais recente do QDK (determinada no **passo 3**). Esses pacotes seguem os padrões de nomenclatura abaixo:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        As referências aos pacotes têm o formato seguinte:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Guarde o ficheiro atualizado.

    - Restaure as dependências do projeto da seguinte forma:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Navegue para a pasta que contém o projeto principal e execute:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Com os projetos Q# já atualizados, siga as instruções abaixo para atualizar o próprio QDK.

## <a name="updating-the-qdk"></a>Atualizar o QDK

O processo de atualização do QDK varia de acordo com a linguagem e o ambiente de desenvolvimento.
Selecione o seu ambiente de desenvolvimento abaixo:

* [Python: atualizar a extensão IQ#](#update-iq-for-python)
* [Jupyter Notebook: atualizar a extensão IQ#](#update-iq-for-jupyter-notebooks)
* [Visual Studio: atualizar a extensão QDK](#update-visual-studio-qdk-extension)
* [VS Code: atualizar a extensão QDK](#update-vs-code-qdk-extension)
* [Linha de comandos e C#: atualizar os modelos de projetos](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Atualizar o IQ# para Python

1. Atualize o kernel `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifique a versão de `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Deverá ver o resultado seguinte:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Não se preocupe se a versão de `iqsharp` for superior; deverá corresponder à [versão mais recente](xref:microsoft.quantum.relnotes).

3. Atualize o pacote `qsharp`

    ```
    pip install qsharp --upgrade
    ```

4. Verifique a versão de `qsharp`

    ```
    pip show qsharp
    ```

    Deverá ver o resultado seguinte:

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Execute o seguinte comando a partir da localização dos ficheiros `.qs`

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. Agora, pode utilizar a versão atualizada do QDK para executar os seus programas quânticos já existentes.

### <a name="update-iq-for-jupyter-notebooks"></a>Atualizar o IQ# para Jupyter Notebook

1. Atualize o kernel `iqsharp`

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verifique a versão de `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    A saída deve ser semelhante ao seguinte:

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Não se preocupe se a versão de `iqsharp` for superior; deverá corresponder à [versão mais recente](xref:microsoft.quantum.relnotes).

3. Execute o seguinte comando a partir de uma célula no Jupyter Notebook:

    ```
    %workspace reload
    ```

4. Agora, já pode abrir um bloco de notas do Jupyter existente e executá-lo com o QDK atualizado.

### <a name="update-visual-studio-qdk-extension"></a>Atualizar a extensão QDK do Visual Studio

1. Atualizar a extensão Q# do Visual Studio

    - O Visual Studio pede-lhe que aceite as atualizações à [extensão Quantum do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Aceite a atualização

    > [!NOTE]
    > Os modelos de projetos são atualizados com a extensão e só se aplicam a projetos recém-criados. O código dos projetos já existentes não é atualizado quando a extensão é atualizada.

### <a name="update-vs-code-qdk-extension"></a>Atualizar a extensão QDK do VS Code

1. Atualize a extensão Quantum do VS Code

    - Reinicie o VS Code
    - Navegue para o separador **Extensions** (Extensões)
    - Selecione a extensão **Microsoft Quantum Development Kit for Visual Studio Code**
    - Recarregue a extensão

2. Atualize os modelos de projetos quânticos:

   - Aceda a **Ver** -> **Paleta de Comandos**
   - Selecione **Q#: Instalar modelos de projetos**
   - Ao fim de alguns segundos, deverá receber um pop-up com a mensagem "project templates installed successfully" ("modelos de projetos instalados com êxito")

### <a name="c-using-the-dotnet-command-line-tool"></a>C# com a ferramenta de linha de comandos `dotnet`

1. Atualize os modelos de projetos quânticos para .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
