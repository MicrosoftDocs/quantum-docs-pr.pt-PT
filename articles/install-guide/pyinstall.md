---
title: Programar com Q# + Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: e1b8a0c68b3ac0c059c6de6e478593321764ff88
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680154"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="2bf22-102">Programar com Q# + Python</span><span class="sxs-lookup"><span data-stu-id="2bf22-102">Develop with Q# + Python</span></span>

<span data-ttu-id="2bf22-103">Instale o QDK para desenvolver programas de anfitriões Python para ligar para as operações Q#.</span><span class="sxs-lookup"><span data-stu-id="2bf22-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="2bf22-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bf22-104">Pre-requisites</span></span>

    - <span data-ttu-id="2bf22-105">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="2bf22-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="2bf22-106">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="2bf22-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="2bf22-107">.NET Core SDK 3.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="2bf22-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="2bf22-108">Instale `qsharp` o pacote, um pacote Python que permite o interop entre Q# e Python.</span><span class="sxs-lookup"><span data-stu-id="2bf22-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="2bf22-109">Instale o IQ#, um núcleo utilizado pela Jupyter e python que fornece a funcionalidade central para a compilação e execução de operações Q#.</span><span class="sxs-lookup"><span data-stu-id="2bf22-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="2bf22-110">Embora possa utilizar Q# com Python em qualquer IDE, recomendamos vivamente a utilização do Código do Estúdio Visual (Código VS) IDE para as suas aplicações Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="2bf22-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="2bf22-111">Ao utilizar o Visual Studio Code e a extensão qDK Visual Studio Code, você tem acesso a uma funcionalidade mais rica.</span><span class="sxs-lookup"><span data-stu-id="2bf22-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="2bf22-112">Instalar [código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="2bf22-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="2bf22-113">Instale a [extensão QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="2bf22-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="2bf22-114">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="2bf22-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="2bf22-115">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="2bf22-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="2bf22-116">Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="2bf22-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="2bf22-117">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="2bf22-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="2bf22-118">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="2bf22-118">Verify the output.</span></span> <span data-ttu-id="2bf22-119">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="2bf22-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="2bf22-120">Você também pode usar os cadernos Python Jupyter para escrever o programa clássico Python e chamar operações Q# a partir das células.</span><span class="sxs-lookup"><span data-stu-id="2bf22-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="2bf22-121">O código Python é apenas um programa python normal.</span><span class="sxs-lookup"><span data-stu-id="2bf22-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="2bf22-122">Passos seguintes?</span><span class="sxs-lookup"><span data-stu-id="2bf22-122">What's next?</span></span>

<span data-ttu-id="2bf22-123">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="2bf22-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
