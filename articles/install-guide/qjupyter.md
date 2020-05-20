---
title: Programar com Q# Jupyter Notebooks
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660766"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="f0228-102">Programar com Q# Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="f0228-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="f0228-103">Instale o QDK para desenvolver operações q# em Cadernos Q# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="f0228-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="f0228-104">Os Cadernos Jupyter permitem a execução do código no local juntamente com instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="f0228-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="f0228-105">Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="f0228-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="f0228-106">Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.</span><span class="sxs-lookup"><span data-stu-id="f0228-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="f0228-107">IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.</span><span class="sxs-lookup"><span data-stu-id="f0228-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="f0228-108">Em Q# Jupyter Notebooks só pode executar código Q# e as operações não podem ser chamadas a partir de programas de acolhimento externos (por exemplo, ficheiros Python ou C#).</span><span class="sxs-lookup"><span data-stu-id="f0228-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="f0228-109">Este ambiente não é apropriado se o seu objetivo é combinar um programa de anfitriões clássico seleto externo com o programa quântico.</span><span class="sxs-lookup"><span data-stu-id="f0228-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="f0228-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f0228-110">Pre-requisites</span></span>

    - <span data-ttu-id="f0228-111">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="f0228-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="f0228-112">Caderno jupyter</span><span class="sxs-lookup"><span data-stu-id="f0228-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="f0228-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="f0228-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="f0228-114">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="f0228-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="f0228-115">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="f0228-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f0228-116">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="f0228-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="f0228-117">Para abrir o Caderno Jupyter, copie e cole o URL fornecido pela linha de comando no seu navegador.</span><span class="sxs-lookup"><span data-stu-id="f0228-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="f0228-118">Crie um Caderno Jupyter com um núcleo Q# e adicione o seguinte código à primeira célula de caderno:</span><span class="sxs-lookup"><span data-stu-id="f0228-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="f0228-119">Execute esta célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="f0228-119">Run this cell of the notebook:</span></span>

        ![Célula de caderno jupyter com código Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="f0228-121">Deverá ver `SayHello` na saída da célula.</span><span class="sxs-lookup"><span data-stu-id="f0228-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="f0228-122">Ao ser recorrido no Caderno Jupyter, o código Q# é compilado e o caderno produz o nome da operação(s) que encontra.</span><span class="sxs-lookup"><span data-stu-id="f0228-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="f0228-123">Numa nova célula, execute a operação que acabou de criar (num simulador) utilizando o `%simulate` comando:</span><span class="sxs-lookup"><span data-stu-id="f0228-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Célula de caderno jupyter com %simulamagia](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="f0228-125">Deve ver a mensagem impressa no ecrã juntamente com o resultado da operação que invocou (aqui, vemos a tuple vazia porque a `()` nossa operação simplesmente devolve um `Unit` tipo).</span><span class="sxs-lookup"><span data-stu-id="f0228-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0228-126">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="f0228-126">Next steps</span></span>

<span data-ttu-id="f0228-127">Agora que instalou o QDK para Os Cadernos Q# Jupyter, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) escrevendo o seu código Q# diretamente dentro do ambiente jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="f0228-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="f0228-128">Para mais exemplos do que pode fazer com os Cadernos Q# Jupyter, por favor dê uma olhada em:</span><span class="sxs-lookup"><span data-stu-id="f0228-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="f0228-129">[Introdução a Q# e Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="f0228-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="f0228-130">Lá você encontrará um Caderno Q# Jupyter que mostra como usar Q# neste ambiente.</span><span class="sxs-lookup"><span data-stu-id="f0228-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="f0228-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção de tutoriais auto-pacatos e conjuntos de exercícios de programação sob a forma de Cadernos Q# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="f0228-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="f0228-132">Os [cadernos tutoriais Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="f0228-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="f0228-133">Os Quantum Katas destinam-se a ensinar-lhe elementos de computação quântica e programação Q# ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f0228-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="f0228-134">São um excelente exemplo do tipo de conteúdo que se pode criar com os Cadernos Q# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="f0228-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
