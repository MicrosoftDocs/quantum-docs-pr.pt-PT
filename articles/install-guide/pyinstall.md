---
title: Desenvolver com Q# e Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630292"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="51e26-102">Desenvolver com Q# e Python</span><span class="sxs-lookup"><span data-stu-id="51e26-102">Develop with Q# and Python</span></span>

<span data-ttu-id="51e26-103">Instale o QDK para desenvolver programas de anfitrião Python para ligar para as operações Q#.</span><span class="sxs-lookup"><span data-stu-id="51e26-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="51e26-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="51e26-104">Prerequisites</span></span>

    - <span data-ttu-id="51e26-105">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="51e26-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="51e26-106">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="51e26-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="51e26-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="51e26-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="51e26-108">Instale o `qsharp` pacote, um pacote Python que permite o interop entre Q# e Python.</span><span class="sxs-lookup"><span data-stu-id="51e26-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="51e26-109">Instale o IQ#, um núcleo utilizado pela Jupyter e pela Python que fornece a funcionalidade principal para compilar e executar operações Q#.</span><span class="sxs-lookup"><span data-stu-id="51e26-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="51e26-110">Se tiver um erro durante o `dotnet iqsharp install` passo, abra uma nova janela do terminal e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="51e26-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="51e26-111">Se isto ainda não funcionar, tente localizar a ferramenta instalada `dotnet-iqsharp` (no Windows, `dotnet-iqsharp.exe` ) e em execução:</span><span class="sxs-lookup"><span data-stu-id="51e26-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="51e26-112">onde `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta no seu sistema de `dotnet-iqsharp` ficheiros.</span><span class="sxs-lookup"><span data-stu-id="51e26-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="51e26-113">Normalmente, isto será na `.dotnet/tools` pasta do perfil do utilizador.</span><span class="sxs-lookup"><span data-stu-id="51e26-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="51e26-114">Enquanto pode utilizar Q# com Python em qualquer IDE, recomendamos vivamente a utilização do Código de Estúdio Visual (Código VS) IDE para as suas aplicações Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="51e26-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="51e26-115">Ao utilizar o Código do Estúdio Visual e a extensão QDK Visual Studio Code, você tem acesso a funcionalidades mais ricas.</span><span class="sxs-lookup"><span data-stu-id="51e26-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="51e26-116">Instalar [código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="51e26-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="51e26-117">Instale a [extensão QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="51e26-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="51e26-118">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="51e26-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="51e26-119">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="51e26-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="51e26-120">Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="51e26-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="51e26-121">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="51e26-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="51e26-122">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="51e26-122">Verify the output.</span></span> <span data-ttu-id="51e26-123">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="51e26-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="51e26-124">Você também pode usar os cadernos Python Jupyter para escrever o programa python clássico e chamar as operações Q# das células.</span><span class="sxs-lookup"><span data-stu-id="51e26-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="51e26-125">O código Python é apenas um programa piton normal.</span><span class="sxs-lookup"><span data-stu-id="51e26-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51e26-126">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="51e26-126">Next steps</span></span>

<span data-ttu-id="51e26-127">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="51e26-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
