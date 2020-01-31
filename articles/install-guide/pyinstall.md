---
title: Desenvolver com Q# + Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831006"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="8c00c-102">Desenvolver com Q# + Python</span><span class="sxs-lookup"><span data-stu-id="8c00c-102">Develop with Q# + Python</span></span>

<span data-ttu-id="8c00c-103">Instale o QDK para desenvolver programas de anfitriões Python para ligar para as operações Q#.</span><span class="sxs-lookup"><span data-stu-id="8c00c-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="8c00c-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8c00c-104">Pre-requisites</span></span>

    - <span data-ttu-id="8c00c-105">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8c00c-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="8c00c-106">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="8c00c-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="8c00c-107">.NET Core SDK 3.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8c00c-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="8c00c-108">Instale o pacote `qsharp`, um pacote Python que permite o interop entre Q# e Python.</span><span class="sxs-lookup"><span data-stu-id="8c00c-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="8c00c-109">Instale `iqsharp`, um núcleo utilizado pela Jupyter e python que fornece a funcionalidade principal para a compilação e execução de operações Q#.</span><span class="sxs-lookup"><span data-stu-id="8c00c-109">Install `iqsharp`, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="8c00c-110">Embora possa utilizar Q# com Python em qualquer IDE, recomendamos vivamente a utilização do Código do Estúdio Visual (Código VS) IDE para as suas aplicações Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="8c00c-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="8c00c-111">Ao utilizar o Visual Studio Code e a extensão qDK Visual Studio Code, você tem acesso a uma funcionalidade mais rica.</span><span class="sxs-lookup"><span data-stu-id="8c00c-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="8c00c-112">Instalar [código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="8c00c-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="8c00c-113">Instale a [extensão QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="8c00c-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="8c00c-114">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="8c00c-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8c00c-115">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="8c00c-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="8c00c-116">Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="8c00c-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="8c00c-117">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="8c00c-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="8c00c-118">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="8c00c-118">Verify the output.</span></span> <span data-ttu-id="8c00c-119">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="8c00c-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="8c00c-120">Você também pode usar os cadernos Python Jupyter para escrever o programa clássico Python e chamar operações Q# a partir das células.</span><span class="sxs-lookup"><span data-stu-id="8c00c-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="8c00c-121">O código Python é apenas um programa python normal.</span><span class="sxs-lookup"><span data-stu-id="8c00c-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="8c00c-122">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="8c00c-122">What's next?</span></span>

<span data-ttu-id="8c00c-123">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="8c00c-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
