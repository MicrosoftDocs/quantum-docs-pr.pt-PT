---
title: Instalar o Microsoft Quantum Development Kit (QDK)
description: Como instalar o Microsoft Quantum Development Kit para diferentes ambientes.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: ee8d210d67a20cfea3bdc36162efc47f021a6dc6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885472"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="b7a70-103">Instalar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b7a70-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b7a70-104">Saiba como instalar o Microsoft Quantum Development Kit (QDK), para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="b7a70-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="b7a70-105">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="b7a70-105">The QDK consists of:</span></span>

- <span data-ttu-id="b7a70-106">Linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="b7a70-106">The Q# programming language</span></span>
- <span data-ttu-id="b7a70-107">Um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="b7a70-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="b7a70-108">APIs para as linguagens Python e .NET (C#, F# e VB.NET) para executar programas quânticos escritos em Q#</span><span class="sxs-lookup"><span data-stu-id="b7a70-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="b7a70-109">Ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="b7a70-109">Tools to facilitate your development</span></span>

<span data-ttu-id="b7a70-110">Os programas Q# podem ser executados como aplicações autónomas com o Visual Studio Code ou através de Blocos de Notas do Jupyter com o kernel IQ# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="b7a70-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="b7a70-111">Também podem ser emparelhados com um programa anfitrião escrito numa linguagem .NET (tipicamente C# ) ou Python, o que permite chamar operações quânticas de dentro de um programa clássico.</span><span class="sxs-lookup"><span data-stu-id="b7a70-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="b7a70-112">Os fluxos de trabalho de cada uma destas configurações são descritos e comparados em [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="b7a70-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="b7a70-113">Para prosseguir com a instalação do QDK e criar projetos Q#, selecione a sua configuração preferida:</span><span class="sxs-lookup"><span data-stu-id="b7a70-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="b7a70-114">[Desenvolver com aplicações de linha de comandos do Q#](xref:microsoft.quantum.install.standalone) - Escolha esta abordagem para trabalhar com o Q# a partir da linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="b7a70-114">[Develop with Q# command line applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="b7a70-115">Não requer um controlador ou um programa anfitrião como acontece com as opções abaixo.</span><span class="sxs-lookup"><span data-stu-id="b7a70-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="b7a70-116">[Desenvolver com o Jupyter Notebook em Q#](xref:microsoft.quantum.install.jupyter) - Selecione este ambiente para executar código Q# em células que tenham texto incorporado ou para criar tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="b7a70-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="b7a70-117">[Desenvolver com Q# e Python](xref:microsoft.quantum.install.python) - Permite-lhe combinar o Python e o Q# para criar um programa anfitrião em Python que chame operações do Q#.</span><span class="sxs-lookup"><span data-stu-id="b7a70-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="b7a70-118">[Desenvolver com Q# e .NET](xref:microsoft.quantum.install.cs) - Combine C#, F# ou VB.NET com o Q# para criar um programa anfitrião em .NET que chame operações do Q#.</span><span class="sxs-lookup"><span data-stu-id="b7a70-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
