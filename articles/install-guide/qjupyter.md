---
title: Desenvolver com cadernos Q# Jupyter
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 3302a9bd0652b2dea86b844058bf8303ee7a4a7f
ms.sourcegitcommit: c85c1b439807ac576d3a11aadca307d57b059673
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/18/2020
ms.locfileid: "83551044"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="c82b7-102">Desenvolver com cadernos Q# Jupyter</span><span class="sxs-lookup"><span data-stu-id="c82b7-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="c82b7-103">Instale o QDK para desenvolver operações q# em Cadernos Q# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="c82b7-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="c82b7-104">Os Cadernos Jupyter permitem a execução do código no local juntamente com instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="c82b7-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="c82b7-105">Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="c82b7-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="c82b7-106">Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.</span><span class="sxs-lookup"><span data-stu-id="c82b7-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="c82b7-107">IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.</span><span class="sxs-lookup"><span data-stu-id="c82b7-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="c82b7-108">Em Q# Jupyter Notebooks só pode executar código Q# e as operações não podem ser chamadas a partir de programas de acolhimento externos (por exemplo, ficheiros Python ou C#).</span><span class="sxs-lookup"><span data-stu-id="c82b7-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="c82b7-109">Este ambiente não é apropriado se o seu objetivo é combinar um programa de anfitriões clássico seleto externo com o programa quântico.</span><span class="sxs-lookup"><span data-stu-id="c82b7-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="c82b7-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c82b7-110">Pre-requisites</span></span>

    - <span data-ttu-id="c82b7-111">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="c82b7-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="c82b7-112">Caderno jupyter</span><span class="sxs-lookup"><span data-stu-id="c82b7-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="c82b7-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="c82b7-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="c82b7-114">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="c82b7-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c82b7-115">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="c82b7-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c82b7-116">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="c82b7-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="c82b7-117">Para abrir a cópia do portátil jupyter e colar o URL fornecido pela linha de comando no seu navegador.</span><span class="sxs-lookup"><span data-stu-id="c82b7-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="c82b7-118">Crie um Jupyter Notebook com um kernel Q# e adicione o seguinte código à primeira célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="c82b7-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="c82b7-119">Execute esta célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="c82b7-119">Run this cell of the notebook:</span></span>

        ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="c82b7-121">Deverá ver `SayHello` na saída da célula.</span><span class="sxs-lookup"><span data-stu-id="c82b7-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="c82b7-122">Ao executar em Jupyter Notebooks, o código Q# é compilado e o bloco de notas produz o nome das operações que encontra.</span><span class="sxs-lookup"><span data-stu-id="c82b7-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="c82b7-123">Numa nova célula, execute a operação que acabou de criar (num simulador) utilizando o `%simulate` comando:</span><span class="sxs-lookup"><span data-stu-id="c82b7-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Célula do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="c82b7-125">Deve ver a mensagem impressa no ecrã juntamente com o resultado da operação que invocou (aqui, vemos a tuple vazia porque a `()` nossa operação simplesmente devolve um `Unit` tipo).</span><span class="sxs-lookup"><span data-stu-id="c82b7-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c82b7-126">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="c82b7-126">Next steps</span></span>

<span data-ttu-id="c82b7-127">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="c82b7-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
