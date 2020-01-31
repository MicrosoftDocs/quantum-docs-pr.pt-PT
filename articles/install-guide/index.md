---
title: Saiba como instalar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820713"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="37772-102">Instalar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="37772-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="37772-103">Saiba como instalar o Microsoft Quantum Development Kit (QDK), para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="37772-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="37772-104">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="37772-104">The QDK consists of:</span></span>

- <span data-ttu-id="37772-105">linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="37772-105">the Q# programming language</span></span>
- <span data-ttu-id="37772-106">um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="37772-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="37772-107">APIs para Python e linguagens .NET (ou seja, C#, F# e VB.NET) para executar programas quânticos escritos em Q#</span><span class="sxs-lookup"><span data-stu-id="37772-107">APIs for Python and .NET languages (i.e.: C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="37772-108">ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="37772-108">tools to facilitate your development</span></span>

<span data-ttu-id="37772-109">Muitas vezes, os programas em Q# são emparelhados com um programa anfitrião escrito numa linguagem .NET (geralmente C#) ou em Python.</span><span class="sxs-lookup"><span data-stu-id="37772-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="37772-110">Dessa forma, podemos chamar operações quânticas a partir de um programa clássico.</span><span class="sxs-lookup"><span data-stu-id="37772-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="37772-111">Além disso, o QDK oferece suporte de Q# para Jupyter Notebook com o kernel IQ# para Jupyter.</span><span class="sxs-lookup"><span data-stu-id="37772-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="37772-112">O QDK está disponível para vários ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="37772-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="37772-113">Selecione a sua configuração preferida de entre as secções abaixo:</span><span class="sxs-lookup"><span data-stu-id="37772-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="37772-114">[Instalar Q# para C#:](xref:microsoft.quantum.install.cs) escolha este ambiente se quiser combinar C# e Q# para criar um programa anfitrião em C# que chame operações em Q#.</span><span class="sxs-lookup"><span data-stu-id="37772-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="37772-115">[Instalar Q# para Python:](xref:microsoft.quantum.install.python) escolha este ambiente se quiser combinar Python e Q# para criar um programa anfitrião em Python que chame operações em Q#.</span><span class="sxs-lookup"><span data-stu-id="37772-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="37772-116">[Instalar Q# para Jupyter Notebook:](xref:microsoft.quantum.install.jupyter) escolha este ambiente para executar código Q# em células que tenham texto incorporado ou para criar tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="37772-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="37772-117">Não o escolha se quiser combinar Q# com um programa anfitrião clássico externo.</span><span class="sxs-lookup"><span data-stu-id="37772-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
