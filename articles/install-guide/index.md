---
title: Saiba como instalar o Microsoft Quantum Development Kit (QDK)
description: Como instalar o Microsoft Quantum Development kit para ambientes C#, Python e Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680198"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="53c88-103">Instalar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="53c88-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="53c88-104">Saiba como instalar o Microsoft Quantum Development Kit (QDK), para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="53c88-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="53c88-105">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="53c88-105">The QDK consists of:</span></span>

- <span data-ttu-id="53c88-106">linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="53c88-106">the Q# programming language</span></span>
- <span data-ttu-id="53c88-107">um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="53c88-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="53c88-108">APIs para as linguagens Python e .NET (C#, F# e VB.NET) para executar programas quânticos escritos em Q#</span><span class="sxs-lookup"><span data-stu-id="53c88-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="53c88-109">ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="53c88-109">tools to facilitate your development</span></span>

<span data-ttu-id="53c88-110">Muitas vezes, os programas em Q# são emparelhados com um programa anfitrião escrito numa linguagem .NET (geralmente C#) ou em Python.</span><span class="sxs-lookup"><span data-stu-id="53c88-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="53c88-111">Dessa forma, podemos chamar operações quânticas a partir de um programa clássico.</span><span class="sxs-lookup"><span data-stu-id="53c88-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="53c88-112">Além disso, o QDK oferece suporte de Q# para Jupyter Notebook com o kernel IQ# para Jupyter.</span><span class="sxs-lookup"><span data-stu-id="53c88-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="53c88-113">O QDK está disponível para vários ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="53c88-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="53c88-114">Selecione a sua configuração preferida de entre as secções abaixo:</span><span class="sxs-lookup"><span data-stu-id="53c88-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="53c88-115">[Aplicação de linha de comandos do Q#:](xref:microsoft.quantum.install.standalone) escolha esta abordagem se quiser trabalhar com o Q# a partir da linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="53c88-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="53c88-116">Não requer um controlador ou um programa anfitrião como acontece com as opções abaixo.</span><span class="sxs-lookup"><span data-stu-id="53c88-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="53c88-117">[Instalar Q# para Jupyter Notebook:](xref:microsoft.quantum.install.jupyter) escolha este ambiente para executar código Q# em células que tenham texto incorporado ou para criar tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="53c88-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="53c88-118">[Desenvolver com o Q# e Python:](xref:microsoft.quantum.install.python) se quiser combinar o Python e o Q# para criar um programa anfitrião em Python que chame operações do Q#.</span><span class="sxs-lookup"><span data-stu-id="53c88-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="53c88-119">[Desenvolver com o Q# e C# ou F#:](xref:microsoft.quantum.install.cs) se quiser combinar o C# ou F# e Q# para criar um programa anfitrião em .NET que chame operações do Q#.</span><span class="sxs-lookup"><span data-stu-id="53c88-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
