---
title: Atualizar o Kit de Desenvolvimento Quântico (QDK)
description: Descreve como atualizar os seus projetos Q# e o Microsoft Quantum Development Kit para a versão atual.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327578"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Atualizar o Kit de Desenvolvimento Quântico da Microsoft (QDK)

Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.

Este artigo pressupõe que já tem o QDK instalado. Se estiver a instalar pela primeira vez, consulte o [guia de instalação](xref:microsoft.quantum.install).

Recomendamos manter-nos atualizados com o mais recente lançamento do QDK. Siga este guia de atualização para atualizar para a versão QDK mais recente. O processo é composto por duas partes:
1. Atualizar os ficheiros e projetos Q# existentes para alinhar o seu código com qualquer sintaxe atualizada.
2. Atualizar o próprio QDK para o seu ambiente de desenvolvimento escolhido.

## <a name="updating-q-projects"></a>Atualizar projetos Q# 

Independentemente de estar a utilizar C# ou Python para acolher operações Q#, siga estas instruções para atualizar os seus projetos Q#.

1. Em primeiro lugar, verifique se tem a versão mais recente do [.NET Core SDK 3.1](https://dotnet.microsoft.com/download). Executar o seguinte comando na pronta de comando:

    ```dotnetcli
    dotnet --version
    ```

    Verifique se a saída é `3.1.100` ou superior. Caso contrário, instale a [versão mais recente](https://dotnet.microsoft.com/download) e verifique novamente. Em seguida, siga as instruções abaixo, dependendo da sua configuração (Visual Studio, Visual Studio Code ou diretamente a linha de comando).

### <a name="update-q-projects-in-visual-studio"></a>Atualizar projetos Q# em Visual Studio
 
1. Atualização para a versão mais recente do Visual Studio 2019, consulte [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obter instruções.
2. Abra a sua solução no Visual Studio.
3. No menu, selecione **Build**  ->  **Clean Solution**.
4. Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para `netcoreapp3.1` (ou `netstandard2.1` se é um projeto de biblioteca).
    Ou seja, editar linhas do formulário:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui.](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)

5. Em cada um dos ficheiros .csproj, desajei o SDK, `Microsoft.Quantum.Sdk` como indicado na linha abaixo. Por favor, note que o número da versão deve ser o mais recente disponível, e pode determiná-lo revendo as [notas de lançamento](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Guarde e feche todos os ficheiros da sua solução.

7. Selecione **ferramentas**  ->  **comando**  ->  **de programador de**linha . Em alternativa, pode utilizar a consola de gestão de pacotes no Visual Studio.

8. Para cada projeto na solução, executar o seguinte comando para **remover** este pacote:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Se os seus projetos utilizarem quaisquer outros pacotes Microsoft.Quantum ou Microsoft.Azure.Quantum (por exemplo, Microsoft.Quantum.Nummerics), executar o comando **de adicionar** para estes atualizarem a versão utilizada.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Feche a solicitação de comando e selecione **a**  ->  **solução** Build Build *(não* selecione a Solução de Reconstrução).

Pode agora antecipar-se para [atualizar a extensão QDK do Seu Estúdio Visual](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Atualizar projetos Q# em Visual Studio Code

1. No Código do Estúdio Visual, abra a pasta que contém o projeto para atualizar.
2. Selecione **Terminal**  ->  **Novo Terminal**Terminal .
3. Siga as instruções de atualização utilizando a linha de comando (diretamente abaixo).

### <a name="update-q-projects-using-the-command-line"></a>Atualizar projetos Q# usando a linha de comando

1. Navegue para a pasta que contém o seu ficheiro principal do projeto.

2. Execute o seguinte comando:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Determine a versão atual do QDK. Para encontrá-lo, pode rever as [notas de lançamento.](https://docs.microsoft.com/quantum/relnotes/) A versão será num formato semelhante a `0.11.2006.207` .

4. Em cada um dos seus `.csproj` ficheiros, ver os seguintes passos:

    - Atualizar o quadro-alvo para `netcoreapp3.1` (ou `netstandard2.1` se é um projeto de biblioteca). Ou seja, editar linhas do formulário:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui.](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)

    - Substitua a referência ao SDK na definição do projeto. Certifique-se de que o número da versão corresponde ao valor determinado no **passo 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Remova a referência à embalagem `Microsoft.Quantum.Development.Kit` se estiver presente, que será especificada na seguinte rubrica:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Atualize a versão de todos os pacotes Da Microsoft Quantum para a versão mais recente do QDK (determinada no **passo 3).** Estes pacotes têm o nome dos seguintes padrões:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        As referências aos pacotes têm o seguinte formato:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Guarde o ficheiro atualizado.

    - Restaurar as dependências do projeto, fazendo o seguinte:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Volte para a pasta que contém o seu projeto principal e corra:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Com os seus projetos Q# agora atualizados, siga as instruções abaixo para atualizar o próprio QDK.

## <a name="updating-the-qdk"></a>Atualizar o QDK

O processo de atualização do QDK varia consoante a sua linguagem e ambiente de desenvolvimento.
Selecione o seu ambiente de desenvolvimento abaixo.

* [Python: atualize a extensão IQ#](#update-iq-for-python)
* [Jupyter Notebooks: atualize a extensão do QI#](#update-iq-for-jupyter-notebooks)
* [Visual Studio: atualize a extensão QDK](#update-visual-studio-qdk-extension)
* [Código VS: atualizar a extensão QDK](#update-vs-code-qdk-extension)
* [Linha de comando e C#: atualizar modelos de projeto](#c-using-the-dotnet-command-line-tool)


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

    Não se preocupe se a sua `iqsharp` versão for maior, deverá corresponder ao [último lançamento](xref:microsoft.quantum.relnotes).

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

6. Agora pode utilizar a versão QDK atualizada para executar os seus programas quânticos existentes.

### <a name="update-iq-for-jupyter-notebooks"></a>Atualização QI# para Cadernos Jupyter

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

    Não se preocupe se a sua `iqsharp` versão for maior, deverá corresponder ao [último lançamento](xref:microsoft.quantum.relnotes).

3. Executar o seguinte comando a partir de uma célula no seu Caderno Jupyter:

    ```
    %workspace reload
    ```

4. Agora pode abrir um caderno Jupyter existente e executá-lo com o QDK atualizado.

### <a name="update-visual-studio-qdk-extension"></a>Atualizar extensão QDK do Estúdio Visual

1. Atualizar a extensão do Estúdio Visual Q#

    - Visual Studio pede-lhe para aceitar atualizações para a [extensão](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) do Quantum Visual Studio
    - Aceite a atualização

    > [!NOTE]
    > Os modelos do projeto são atualizados com a extensão. Os modelos atualizados aplicam-se apenas a projetos recém-criados. O código para os seus projetos existentes não é atualizado quando a extensão é atualizada.

### <a name="update-vs-code-qdk-extension"></a>Atualização extensão QDK do código VS

1. Atualizar a extensão do Código VS Quântico

    - Reiniciar código VS
    - Navegue para o **separador Extensões**
    - Selecione o **Kit de Desenvolvimento Quântico da Microsoft para** extensão visual Studio Code
    - Recarregar a extensão

2. Atualize os modelos de projeto quântico:

   - Ir para **ver paleta**  ->  **de comando**
   - Selecione **Q#: Instale modelos de projeto**
   - Após alguns segundos, você deve obter um popup confirmando "modelos de projeto instalados com sucesso"

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, utilizando a `dotnet` ferramenta de linha de comando

1. Atualize os modelos de projeto quântico para .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
