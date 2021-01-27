---
title: Configurar o Microsoft Quantum Development Kit (QDK)
description: Saiba como configurar o Microsoft Quantum Development Kit para diferentes ambientes.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859032"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="681ba-103">Configurar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="681ba-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="681ba-104">Saiba como configurar o Microsoft Quantum Development Kit (QDK) para o seu ambiente, para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="681ba-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="681ba-105">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="681ba-105">The QDK consists of:</span></span>

- <span data-ttu-id="681ba-106">Linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="681ba-106">The Q# programming language</span></span>
- <span data-ttu-id="681ba-107">Um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="681ba-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="681ba-108">APIs para as linguagens Python e .NET (C#, F# e VB.NET) para executar programas quânticos escritos em Q#</span><span class="sxs-lookup"><span data-stu-id="681ba-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="681ba-109">Ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="681ba-109">Tools to facilitate your development</span></span>

<span data-ttu-id="681ba-110">Os programas Q# podem ser executados como aplicações autónomas com o Visual Studio Code ou o Visual Studio, através do Jupyter Notebook com o kernel IQ# Jupyter ou emparelhado com um programa anfitrião escrito em Python ou numa linguagem .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="681ba-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="681ba-111">Também pode executar programas Q# online com o [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) ou [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="681ba-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="681ba-112">Opções de configuração do QDK</span><span class="sxs-lookup"><span data-stu-id="681ba-112">Options for setting up the QDK</span></span>

<span data-ttu-id="681ba-113">Pode utilizar o QDK de três maneiras:</span><span class="sxs-lookup"><span data-stu-id="681ba-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="681ba-114">Instalar o QDK localmente</span><span class="sxs-lookup"><span data-stu-id="681ba-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="681ba-115">Utilizar o QDK online</span><span class="sxs-lookup"><span data-stu-id="681ba-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="681ba-116">Utilizar uma imagem do Docker para o QDK</span><span class="sxs-lookup"><span data-stu-id="681ba-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="681ba-117">Instalar o QDK localmente</span><span class="sxs-lookup"><span data-stu-id="681ba-117">Install the QDK locally</span></span>

<span data-ttu-id="681ba-118">Pode desenvolver código Q# na maior parte dos seus IDEs favoritos, tal como pode integrar o Q# noutras linguagens, como Python e .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="681ba-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="681ba-119"><b>Código VS</span><span class="sxs-lookup"><span data-stu-id="681ba-119"><b>VS Code</span></span><br><span data-ttu-id="681ba-120">(2019 ou posterior)</b></span><span class="sxs-lookup"><span data-stu-id="681ba-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="681ba-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="681ba-121"><b>Visual Studio</span></span><br><span data-ttu-id="681ba-122">(2019 ou posterior)</b></span><span class="sxs-lookup"><span data-stu-id="681ba-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="681ba-123"><b>Jupyter Notebooks</b></span><span class="sxs-lookup"><span data-stu-id="681ba-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="681ba-124"><b>Linha de comandos</b></span><span class="sxs-lookup"><span data-stu-id="681ba-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="681ba-125"><b>Suporte de SO:</b></span><span class="sxs-lookup"><span data-stu-id="681ba-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="681ba-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="681ba-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="681ba-127">Apenas no Windows</span><span class="sxs-lookup"><span data-stu-id="681ba-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="681ba-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="681ba-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="681ba-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="681ba-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="681ba-130"><b>Q# autónomo</b></span><span class="sxs-lookup"><span data-stu-id="681ba-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="681ba-131"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-132"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-133"><a href="xref:microsoft.quantum.install.jupyter">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-134"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="681ba-135"><b>Q# e Python</b></span><span class="sxs-lookup"><span data-stu-id="681ba-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="681ba-136"><a href="xref:microsoft.quantum.install.python">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-137"><a href="xref:microsoft.quantum.install.python">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-138"><a href="xref:microsoft.quantum.install.python">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-139"><a href="xref:microsoft.quantum.install.python">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="681ba-140"><b>Q# e .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="681ba-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="681ba-141"><a href="xref:microsoft.quantum.install.cs">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-142"><a href="xref:microsoft.quantum.install.cs">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="681ba-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="681ba-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="681ba-144"><a href="xref:microsoft.quantum.install.cs">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="681ba-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="681ba-145">Utilizar o QDK Online</span><span class="sxs-lookup"><span data-stu-id="681ba-145">Use the QDK Online</span></span>

<span data-ttu-id="681ba-146">Também pode desenvolver código Q# sem instalar nada localmente com estas opções:</span><span class="sxs-lookup"><span data-stu-id="681ba-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="681ba-147">Recurso</span><span class="sxs-lookup"><span data-stu-id="681ba-147">Resource</span></span>|<span data-ttu-id="681ba-148">Vantagens</span><span class="sxs-lookup"><span data-stu-id="681ba-148">Advantages</span></span>|<span data-ttu-id="681ba-149">Limitações</span><span class="sxs-lookup"><span data-stu-id="681ba-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="681ba-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="681ba-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="681ba-151">Um ambiente de desenvolvimento online avançado</span><span class="sxs-lookup"><span data-stu-id="681ba-151">A rich online development environment</span></span>  |<span data-ttu-id="681ba-152">Requer um plano e subscrição do Azure</span><span class="sxs-lookup"><span data-stu-id="681ba-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="681ba-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="681ba-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="681ba-154">Experiência de bloco de notas online gratuita</span><span class="sxs-lookup"><span data-stu-id="681ba-154">Free online notebook experience</span></span> |<span data-ttu-id="681ba-155">Sem persistência</span><span class="sxs-lookup"><span data-stu-id="681ba-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="681ba-156">Utilizar o QDK com o Docker</span><span class="sxs-lookup"><span data-stu-id="681ba-156">Use the QDK with Docker</span></span>

<span data-ttu-id="681ba-157">Pode utilizar a nossa imagem do Docker para o QDK na sua instalação local do Docker ou na cloud através de qualquer serviço que suporte imagens do Docker, como o ACI.</span><span class="sxs-lookup"><span data-stu-id="681ba-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="681ba-158">Pode transferir a imagem do Docker IQ# a partir de https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="681ba-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="681ba-159">Também pode utilizar o Docker com um Contentor de Desenvolvimento Remoto do Visual Studio Code para definir rapidamente ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="681ba-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="681ba-160">Para obter mais informações sobre Contentores de Desenvolvimento do VS Code, veja https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="681ba-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="681ba-161">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="681ba-161">Next steps</span></span>

<span data-ttu-id="681ba-162">Os fluxos de trabalho de cada uma destas configurações são descritos e comparados em [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="681ba-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
