---
title: Programar com Q# Jupyter Notebook
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274162"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="0717f-102">Programar com Q# Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="0717f-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="0717f-103">Instale o QDK para desenvolver operações Q# em blocos de notas Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="0717f-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="0717f-104">O Jupyter Notebook permitem executar código no local juntamente com instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="0717f-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="0717f-105">Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="0717f-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="0717f-106">Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.</span><span class="sxs-lookup"><span data-stu-id="0717f-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="0717f-107">IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.</span><span class="sxs-lookup"><span data-stu-id="0717f-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="0717f-108">No Q# Jupyter Notebook, só pode executar código Q# e as operações não podem ser chamadas a partir de programas anfitriões externos (por exemplo, ficheiros Python ou C#).</span><span class="sxs-lookup"><span data-stu-id="0717f-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="0717f-109">Se o seu objetivo for combinar um programa anfitrião clássico externo com o programa quântico, este ambiente não é o indicado.</span><span class="sxs-lookup"><span data-stu-id="0717f-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="0717f-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0717f-110">Prerequisites</span></span>

    - <span data-ttu-id="0717f-111">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="0717f-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="0717f-112">Bloco de Notas do Jupyter</span><span class="sxs-lookup"><span data-stu-id="0717f-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="0717f-113">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="0717f-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="0717f-114">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="0717f-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="0717f-115">Se receber um erro durante o passo `dotnet iqsharp install`, abra uma janela de terminal nova e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="0717f-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="0717f-116">Se continuar a não funcionar, tente localizar a ferramenta `dotnet-iqsharp` instalada (no Windows, `dotnet-iqsharp.exe`) e executar:</span><span class="sxs-lookup"><span data-stu-id="0717f-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="0717f-117">em que `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta `dotnet-iqsharp` no sistema de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="0717f-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="0717f-118">Geralmente, estará em `.dotnet/tools` na pasta de perfil de utilizador.</span><span class="sxs-lookup"><span data-stu-id="0717f-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="0717f-119">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="0717f-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="0717f-120">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="0717f-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="0717f-121">Para abrir o bloco de notas Jupyter Notebook, copie e cole o URL fornecido pela linha de comandos no browser.</span><span class="sxs-lookup"><span data-stu-id="0717f-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="0717f-122">Crie um bloco de notas do Jupyter Notebook com um kernel Q# e adicione o seguinte código à primeira célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="0717f-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="0717f-123">Execute esta célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="0717f-123">Run this cell of the notebook:</span></span>

        ![Célula do bloco de notas do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="0717f-125">Deverá ver `SayHello` na saída da célula.</span><span class="sxs-lookup"><span data-stu-id="0717f-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="0717f-126">Ao executar no Jupyter Notebook, o código Q# é compilado e o bloco de notas produz o nome das operações que encontra.</span><span class="sxs-lookup"><span data-stu-id="0717f-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="0717f-127">Numa célula nova, execute a operação que acabou de criar (num simulador) com o comando `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="0717f-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Célula do bloco de notas do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="0717f-129">Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, vemos a cadeia de identificação vazia `()`, porque a operação deve simplesmente um tipo `Unit`).</span><span class="sxs-lookup"><span data-stu-id="0717f-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0717f-130">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="0717f-130">Next steps</span></span>

<span data-ttu-id="0717f-131">Agora que instalou o QDK para o Q# Jupyter Notebook, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) ao escrever o código Q# diretamente no ambiente do Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="0717f-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="0717f-132">Para obter mais exemplos do que pode fazer com o Q# Jupyter Notebook, veja:</span><span class="sxs-lookup"><span data-stu-id="0717f-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="0717f-133">[Introdução a Q# e ao Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="0717f-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="0717f-134">Aqui, encontrará um bloco de notas Q# Jupyter Notebook que mostra como utilizar o Q# neste ambiente.</span><span class="sxs-lookup"><span data-stu-id="0717f-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="0717f-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção open-source de tutoriais ao seu ritmo e de conjuntos de exercícios de programação na forma de blocos de notas do Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="0717f-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="0717f-136">Os [blocos de notas de tutoriais do Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="0717f-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="0717f-137">Os Quantum katas têm como objetivo ensinar-lhe elementos de computação quântica e programação em Q# ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0717f-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="0717f-138">São um excelente exemplo dos tipos de conteúdos que pode criar com o Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="0717f-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
