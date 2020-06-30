---
title: Programar com Q# e Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274150"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="89a32-102">Programar com Q# e Python</span><span class="sxs-lookup"><span data-stu-id="89a32-102">Develop with Q# and Python</span></span>

<span data-ttu-id="89a32-103">Instale o QDK para desenvolver programas anfitriões Python para chamar operações Q#.</span><span class="sxs-lookup"><span data-stu-id="89a32-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="89a32-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="89a32-104">Prerequisites</span></span>

    - <span data-ttu-id="89a32-105">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="89a32-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="89a32-106">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="89a32-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="89a32-107">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="89a32-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="89a32-108">Instale o pacote `qsharp`, um pacote Python que permite interoperabilidade entre o Q# e o Python.</span><span class="sxs-lookup"><span data-stu-id="89a32-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="89a32-109">Instale o IQ#, um kernel que o Jupyter e o Python utilizam e que proporciona a principal funcionalidade para compilar e executar operações Q#.</span><span class="sxs-lookup"><span data-stu-id="89a32-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="89a32-110">Se receber um erro durante o passo `dotnet iqsharp install`, abra uma janela de terminal nova e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="89a32-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="89a32-111">Se continuar a não funcionar, tente localizar a ferramenta `dotnet-iqsharp` instalada (no Windows, `dotnet-iqsharp.exe`) e executar:</span><span class="sxs-lookup"><span data-stu-id="89a32-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="89a32-112">em que `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta `dotnet-iqsharp` no sistema de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="89a32-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="89a32-113">Geralmente, estará em `.dotnet/tools` na pasta de perfil de utilizador.</span><span class="sxs-lookup"><span data-stu-id="89a32-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="89a32-114">Embora possa utilizar o Q# com o Python em qualquer IDE, recomendamos vivamente utilizar o IDE do Visual Studio Code (VS Code) para as aplicações Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="89a32-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="89a32-115">A utilização do Visual Studio Code e da extensão QDK do Visual Studio Code concede-lhe acesso a funcionalidades mais ricas.</span><span class="sxs-lookup"><span data-stu-id="89a32-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="89a32-116">Instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="89a32-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="89a32-117">Instale a [extensão QDK para o VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="89a32-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="89a32-118">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="89a32-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="89a32-119">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="89a32-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="89a32-120">Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="89a32-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="89a32-121">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="89a32-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="89a32-122">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="89a32-122">Verify the output.</span></span> <span data-ttu-id="89a32-123">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="89a32-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="89a32-124">Também pode utilizar blocos de notas Python Jupyter Notebook para escrever o programa Python clássico e chamar operações Q# a partir das células.</span><span class="sxs-lookup"><span data-stu-id="89a32-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="89a32-125">O código Python é um programa Python normal.</span><span class="sxs-lookup"><span data-stu-id="89a32-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89a32-126">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="89a32-126">Next steps</span></span>

<span data-ttu-id="89a32-127">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="89a32-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
