---
title: Programar com Q# Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577825"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="d0cc9-102">Programar com Q# Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="d0cc9-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="d0cc9-103">Instale o QDK para desenvolver operações Q# em Cadernos Q# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="d0cc9-104">Os Cadernos Jupyter permitem a execução do código no local juntamente com instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="d0cc9-105">Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="d0cc9-106">Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="d0cc9-107">IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="d0cc9-108">Em Q# Jupyter Notebooks só é possível executar o código Q# e as operações não podem ser chamadas a partir de programas de anfitriões externos (por exemplo, ficheiros Python ou C#).</span><span class="sxs-lookup"><span data-stu-id="d0cc9-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="d0cc9-109">Este ambiente não é apropriado se o seu objetivo é combinar um programa de anfitrião clássico externo com o programa quântico.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="d0cc9-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d0cc9-110">Pre-requisites</span></span>

    - <span data-ttu-id="d0cc9-111">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d0cc9-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="d0cc9-112">Caderno Jupyter</span><span class="sxs-lookup"><span data-stu-id="d0cc9-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="d0cc9-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="d0cc9-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="d0cc9-114">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="d0cc9-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="d0cc9-115">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="d0cc9-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="d0cc9-116">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="d0cc9-116">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="d0cc9-117">Para abrir o Bloco de Notas Jupyter, copie e cole o URL fornecido pela linha de comando no seu navegador.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="d0cc9-118">Crie um Caderno Jupyter com um kernel Q# e adicione o seguinte código à primeira célula do portátil:</span><span class="sxs-lookup"><span data-stu-id="d0cc9-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="d0cc9-119">Execute esta célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="d0cc9-119">Run this cell of the notebook:</span></span>

        ![Célula de caderno Jupyter com código Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="d0cc9-121">Deverá ver `SayHello` na saída da célula.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="d0cc9-122">Ao correr no Jupyter Notebook, o código Q# é compilado e o portátil produz o nome da(s) operação(s) que encontra.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="d0cc9-123">Numa nova célula, execute a operação que acabou de criar (num simulador) utilizando o `%simulate` comando:</span><span class="sxs-lookup"><span data-stu-id="d0cc9-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Célula de Caderno Jupyter com %simular magia](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="d0cc9-125">Deve ver a mensagem impressa no ecrã juntamente com o resultado da operação que invocou (aqui, vemos o tuple vazio porque a `()` nossa operação simplesmente devolve um `Unit` tipo).</span><span class="sxs-lookup"><span data-stu-id="d0cc9-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0cc9-126">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="d0cc9-126">Next steps</span></span>

<span data-ttu-id="d0cc9-127">Agora que instalou o QDK para Q# Jupyter Notebooks, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) escrevendo o seu código Q# diretamente dentro do ambiente do Caderno Jupyter.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="d0cc9-128">Para mais exemplos do que pode fazer com os Cadernos Q# Jupyter, por favor dê uma olhada:</span><span class="sxs-lookup"><span data-stu-id="d0cc9-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="d0cc9-129">[Introdução a Q# e Caderno Jupyter](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="d0cc9-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="d0cc9-130">Lá você encontrará um Q# Jupyter Notebook que mostra como usar Q# neste ambiente.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="d0cc9-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção aberta de tutoriais auto-pacatos e conjuntos de exercícios de programação sob a forma de Q# Jupyter Notebooks.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="d0cc9-132">Os [cadernos tutoriais Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="d0cc9-133">As Katas Quânticas destinam-se a ensinar-lhe elementos de computação quântica e programação Q# ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="d0cc9-134">São um excelente exemplo do tipo de conteúdo que se pode criar com os Cadernos Q# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="d0cc9-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
