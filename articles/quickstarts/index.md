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
ms.openlocfilehash: f0c3df1998f9b64ff6544867b83a7afe52b6f46d
ms.sourcegitcommit: fd57a845d013ae4578715d04b1ed1edc1c8ff6b4
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/18/2020
ms.locfileid: "94870826"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="88169-103">Configurar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="88169-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="88169-104">Saiba como configurar o Microsoft Quantum Development Kit (QDK) para o seu ambiente, para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="88169-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="88169-105">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="88169-105">The QDK consists of:</span></span>

- <span data-ttu-id="88169-106">Linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="88169-106">The Q# programming language</span></span>
- <span data-ttu-id="88169-107">Um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="88169-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="88169-108">APIs para as linguagens Python e .NET (C#, F# e VB.NET) para executar programas quânticos escritos em Q#</span><span class="sxs-lookup"><span data-stu-id="88169-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="88169-109">Ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="88169-109">Tools to facilitate your development</span></span>

<span data-ttu-id="88169-110">Os programas Q# podem ser executados como aplicações autónomas com o Visual Studio Code ou o Visual Studio, através do Jupyter Notebook com o kernel IQ# Jupyter ou emparelhado com um programa anfitrião escrito em Python ou numa linguagem .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="88169-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="88169-111">Também pode executar programas Q# online com o [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) ou [Docker](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="88169-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="88169-112">Opções de configuração do QDK</span><span class="sxs-lookup"><span data-stu-id="88169-112">Options for setting up the QDK</span></span>

<span data-ttu-id="88169-113">Pode utilizar o QDK de três maneiras:</span><span class="sxs-lookup"><span data-stu-id="88169-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="88169-114">Instalar o QDK localmente</span><span class="sxs-lookup"><span data-stu-id="88169-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="88169-115">Utilizar o QDK online</span><span class="sxs-lookup"><span data-stu-id="88169-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="88169-116">Utilizar uma imagem do Docker para o QDK</span><span class="sxs-lookup"><span data-stu-id="88169-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="88169-117">Instalar o QDK localmente</span><span class="sxs-lookup"><span data-stu-id="88169-117">Install the QDK locally</span></span>

<span data-ttu-id="88169-118">Pode desenvolver código Q# na maior parte dos seus IDEs favoritos, tal como pode integrar o Q# noutras linguagens, como Python e .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="88169-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="88169-119"><b>Código VS</span><span class="sxs-lookup"><span data-stu-id="88169-119"><b>VS Code</span></span><br><span data-ttu-id="88169-120">(2019 ou posterior)</b></span><span class="sxs-lookup"><span data-stu-id="88169-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="VS Studio" width="50"/><br><span data-ttu-id="88169-121"><b>VS Studio</span><span class="sxs-lookup"><span data-stu-id="88169-121"><b>VS Studio</span></span><br><span data-ttu-id="88169-122">(2019 ou posterior)</b></span><span class="sxs-lookup"><span data-stu-id="88169-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="88169-123"><b>Jupyter Notebooks</b></span><span class="sxs-lookup"><span data-stu-id="88169-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="88169-124"><b>Linha de comandos</b></span><span class="sxs-lookup"><span data-stu-id="88169-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="88169-125"><b>Suporte de SO:</b></span><span class="sxs-lookup"><span data-stu-id="88169-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="88169-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="88169-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="88169-127">Apenas no Windows</span><span class="sxs-lookup"><span data-stu-id="88169-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="88169-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="88169-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="88169-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="88169-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="88169-130"><b>Q# autónomo</b></span><span class="sxs-lookup"><span data-stu-id="88169-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="88169-131"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-132"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-133"><a href="xref:microsoft.quantum.install.jupyter">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-134"><a href="xref:microsoft.quantum.install.standalone">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="88169-135"><b>Q# e Python</b></span><span class="sxs-lookup"><span data-stu-id="88169-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="88169-136"><a href="xref:microsoft.quantum.install.python">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-137"><a href="xref:microsoft.quantum.install.python">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-138"><a href="xref:microsoft.quantum.install.jupyter">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-138"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-139"><a href="xref:microsoft.quantum.install.python">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="88169-140"><b>Q# e .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="88169-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="88169-141"><a href="xref:microsoft.quantum.install.cs">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-142"><a href="xref:microsoft.quantum.install.cs">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="88169-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="88169-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="88169-144"><a href="xref:microsoft.quantum.install.cs">Instalar</a></span><span class="sxs-lookup"><span data-stu-id="88169-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="88169-145">Utilizar o QDK Online</span><span class="sxs-lookup"><span data-stu-id="88169-145">Use the QDK Online</span></span>

<span data-ttu-id="88169-146">Também pode desenvolver código Q# sem instalar nada localmente com estas opções:</span><span class="sxs-lookup"><span data-stu-id="88169-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="88169-147">Recurso</span><span class="sxs-lookup"><span data-stu-id="88169-147">Resource</span></span>|<span data-ttu-id="88169-148">Vantagens</span><span class="sxs-lookup"><span data-stu-id="88169-148">Advantages</span></span>|<span data-ttu-id="88169-149">Limitações</span><span class="sxs-lookup"><span data-stu-id="88169-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="88169-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="88169-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="88169-151">Um ambiente de desenvolvimento online avançado</span><span class="sxs-lookup"><span data-stu-id="88169-151">A rich online development environment</span></span>  |<span data-ttu-id="88169-152">Requer um plano e subscrição do Azure</span><span class="sxs-lookup"><span data-stu-id="88169-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="88169-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="88169-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="88169-154">Experiência de bloco de notas online gratuita</span><span class="sxs-lookup"><span data-stu-id="88169-154">Free online notebook experience</span></span> |<span data-ttu-id="88169-155">Sem persistência</span><span class="sxs-lookup"><span data-stu-id="88169-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="88169-156">Utilizar o QDK com o Docker</span><span class="sxs-lookup"><span data-stu-id="88169-156">Use the QDK with Docker</span></span>

<span data-ttu-id="88169-157">Pode utilizar a nossa imagem do Docker para o QDK na sua instalação local do Docker ou na cloud através de qualquer serviço que suporte imagens do Docker, como o ACI.</span><span class="sxs-lookup"><span data-stu-id="88169-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="88169-158">Pode transferir a imagem do Docker IQ# a partir de https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="88169-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="88169-159">Também pode utilizar o Docker com um Contentor de Desenvolvimento Remoto do Visual Studio Code para definir rapidamente ambientes de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="88169-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="88169-160">Para obter mais informações sobre Contentores de Desenvolvimento do VS Code, veja https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="88169-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="88169-161">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="88169-161">Next steps</span></span>

<span data-ttu-id="88169-162">Os fluxos de trabalho de cada uma destas configurações são descritos e comparados em [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="88169-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
