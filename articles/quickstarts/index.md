---
title: Configurar o Microsoft Quantum Development Kit (QDK)
description: Saiba como configurar o Microsoft Quantum Development Kit para diferentes ambientes.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834487"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="58182-103">Configurar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="58182-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="58182-104">Saiba como configurar o Microsoft Quantum Development Kit (QDK) para o seu ambiente, para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="58182-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="58182-105">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="58182-105">The QDK consists of:</span></span>

- <span data-ttu-id="58182-106">Linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="58182-106">The Q# programming language</span></span>
- <span data-ttu-id="58182-107">Um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="58182-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="58182-108">APIs para as linguagens Python e .NET (C#, F# e VB.NET) para executar programas quânticos escritos em Q#</span><span class="sxs-lookup"><span data-stu-id="58182-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="58182-109">Ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="58182-109">Tools to facilitate your development</span></span>

<span data-ttu-id="58182-110">Os programas Q# podem ser executados como aplicações autónomas com o Visual Studio Code ou o Visual Studio, através do Jupyter Notebook com o kernel IQ# Jupyter ou emparelhado com um programa anfitrião escrito em Python ou numa linguagem .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="58182-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="58182-111">Também pode executar programas Q# online com o [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) ou [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="58182-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="58182-112">Opções de configuração do QDK</span><span class="sxs-lookup"><span data-stu-id="58182-112">Options for setting up the QDK</span></span>

<span data-ttu-id="58182-113">Pode utilizar o QDK de três maneiras:</span><span class="sxs-lookup"><span data-stu-id="58182-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="58182-114">Instalar o QDK localmente</span><span class="sxs-lookup"><span data-stu-id="58182-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="58182-115">Utilizar o QDK online</span><span class="sxs-lookup"><span data-stu-id="58182-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="58182-116">Utilizar uma imagem do Docker para o QDK</span><span class="sxs-lookup"><span data-stu-id="58182-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="58182-117">Instalar o QDK localmente</span><span class="sxs-lookup"><span data-stu-id="58182-117">Install the QDK locally</span></span>

<span data-ttu-id="58182-118">Pode desenvolver código Q# na maior parte dos seus IDEs favoritos, tal como pode integrar o Q# noutras linguagens, como Python e .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="58182-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="58182-119">**VS Code<br>(2019 ou posterior)**</span><span class="sxs-lookup"><span data-stu-id="58182-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="58182-120">**Visual Studio<br>(2019 ou posterior)**</span><span class="sxs-lookup"><span data-stu-id="58182-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="58182-121">**Jupyter Notebooks**</span><span class="sxs-lookup"><span data-stu-id="58182-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="58182-122">**Linha de comandos**</span><span class="sxs-lookup"><span data-stu-id="58182-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="58182-123">**SO**</span><span class="sxs-lookup"><span data-stu-id="58182-123">**OS**</span></span> |<span data-ttu-id="58182-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="58182-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="58182-125">Apenas no Windows</span><span class="sxs-lookup"><span data-stu-id="58182-125">Windows only</span></span> |<span data-ttu-id="58182-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="58182-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="58182-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="58182-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="58182-128">**Q# autónomo**</span><span class="sxs-lookup"><span data-stu-id="58182-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="58182-129">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="58182-130">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="58182-131">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="58182-132">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="58182-133">**Q#  e Python**</span><span class="sxs-lookup"><span data-stu-id="58182-133">**Q#  and Python**</span></span> |[<span data-ttu-id="58182-134">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="58182-135">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="58182-136">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="58182-137">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="58182-138">**Q# e .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="58182-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="58182-139">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="58182-140">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="58182-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="58182-141">&#10006;</span></span> |[<span data-ttu-id="58182-142">Instalar</span><span class="sxs-lookup"><span data-stu-id="58182-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="58182-143">Utilizar o QDK Online</span><span class="sxs-lookup"><span data-stu-id="58182-143">Use the QDK Online</span></span>

<span data-ttu-id="58182-144">Também pode desenvolver código Q# sem instalar nada localmente com estas opções:</span><span class="sxs-lookup"><span data-stu-id="58182-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="58182-145">Recurso</span><span class="sxs-lookup"><span data-stu-id="58182-145">Resource</span></span>|<span data-ttu-id="58182-146">Vantagens</span><span class="sxs-lookup"><span data-stu-id="58182-146">Advantages</span></span>|<span data-ttu-id="58182-147">Limitações</span><span class="sxs-lookup"><span data-stu-id="58182-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="58182-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="58182-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="58182-149">Um ambiente de desenvolvimento online avançado</span><span class="sxs-lookup"><span data-stu-id="58182-149">A rich online development environment</span></span>  |<span data-ttu-id="58182-150">Requer um plano e subscrição do Azure</span><span class="sxs-lookup"><span data-stu-id="58182-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="58182-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="58182-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="58182-152">Experiência de bloco de notas online gratuita</span><span class="sxs-lookup"><span data-stu-id="58182-152">Free online notebook experience</span></span> |<span data-ttu-id="58182-153">Sem persistência</span><span class="sxs-lookup"><span data-stu-id="58182-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="58182-154">Utilizar o QDK com o Docker</span><span class="sxs-lookup"><span data-stu-id="58182-154">Use the QDK with Docker</span></span>

<span data-ttu-id="58182-155">Pode utilizar a nossa imagem do Docker para o QDK na sua instalação local do Docker ou na cloud através de qualquer serviço que suporte imagens do Docker, como o ACI.</span><span class="sxs-lookup"><span data-stu-id="58182-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="58182-156">Pode transferir a imagem do Docker IQ# a partir de https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="58182-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="58182-157">Também pode utilizar o Docker com um Contentor de Desenvolvimento Remoto do Visual Studio Code para definir rapidamente ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="58182-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="58182-158">Para obter mais informações sobre Contentores de Desenvolvimento do VS Code, veja https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="58182-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="58182-159">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="58182-159">Next steps</span></span>

<span data-ttu-id="58182-160">Os fluxos de trabalho de cada uma destas configurações são descritos e comparados em [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="58182-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
