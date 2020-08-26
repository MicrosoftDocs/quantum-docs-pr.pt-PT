---
title: Utilização de bibliotecas adicionais Q#
description: Saiba como adicionar bibliotecas adicionais Q# às suas aplicações quânticas.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: c558e25bf0d906ba6480cd7c41d3ece4ea97c2d1
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863074"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="999de-103">Utilização de Q# bibliotecas adicionais</span><span class="sxs-lookup"><span data-stu-id="999de-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="999de-104">O Kit de Desenvolvimento Quântico fornece uma funcionalidade adicional específica do domínio através de _pacotes NuGet_ que podem ser adicionados aos seus Q# projetos.</span><span class="sxs-lookup"><span data-stu-id="999de-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="999de-105">Q# Biblioteca</span><span class="sxs-lookup"><span data-stu-id="999de-105">Q# Library</span></span>  | <span data-ttu-id="999de-106">Pacote NuGet</span><span class="sxs-lookup"><span data-stu-id="999de-106">NuGet package</span></span> | <span data-ttu-id="999de-107">Notas</span><span class="sxs-lookup"><span data-stu-id="999de-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="999de-108">Q# biblioteca padrão</span><span class="sxs-lookup"><span data-stu-id="999de-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="999de-109">**Microsoft.Quantum.Standard**</span><span class="sxs-lookup"><span data-stu-id="999de-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="999de-110">Incluído por padrão</span><span class="sxs-lookup"><span data-stu-id="999de-110">Included by default</span></span> |
| [<span data-ttu-id="999de-111">Biblioteca de química quântica</span><span class="sxs-lookup"><span data-stu-id="999de-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="999de-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="999de-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="999de-113">Biblioteca numérica quântica</span><span class="sxs-lookup"><span data-stu-id="999de-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="999de-114">**Microsoft.Quantum.Nummerics**</span><span class="sxs-lookup"><span data-stu-id="999de-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="999de-115">Biblioteca de machine learning quântica</span><span class="sxs-lookup"><span data-stu-id="999de-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="999de-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="999de-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="999de-117">Uma vez instalado o Kit de Desenvolvimento Quântico para utilização com o seu ambiente preferido e linguagem de acolhimento, pode facilmente adicionar bibliotecas a projetos individuais Q# sem qualquer instalação adicional.</span><span class="sxs-lookup"><span data-stu-id="999de-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="999de-118">Algumas Q# bibliotecas podem funcionar bem com ferramentas adicionais que funcionam ao lado dos seus Q# programas, ou que se integram com as suas aplicações de anfitrião.</span><span class="sxs-lookup"><span data-stu-id="999de-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="999de-119">Por exemplo, as [instruções de instalação](xref:microsoft.quantum.chemistry.concepts.installation) da biblioteca de química descrevem como usar o pacote [ **Microsoft.Quantum.Chemistry** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) juntamente com a plataforma de química computacional NWChem e como instalar as `qdk-chem` ferramentas da linha de comando para trabalhar com dados de química quântica.</span><span class="sxs-lookup"><span data-stu-id="999de-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-applications-or-net-interopability"></a>[<span data-ttu-id="999de-120">Q# aplicações ou interoabilidade .NET</span><span class="sxs-lookup"><span data-stu-id="999de-120">Q# applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="999de-121">**Pedido de comando ou Código do Estúdio Visual:** Utilizando o pedido de comando por si só ou a partir do Código do Estúdio Visual, pode utilizar o `dotnet` comando para adicionar uma referência de pacote NuGet ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="999de-121">**Command prompt or Visual Studio Code:** Using the command prompt on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="999de-122">Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics,**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="999de-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="999de-123">**Estúdio Visual:** Se estiver a utilizar o Visual Studio 2019 ou mais tarde, pode adicionar pacotes adicionais Q# utilizando o NuGet Package Manager.</span><span class="sxs-lookup"><span data-stu-id="999de-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="999de-124">Para carregar um pacote:</span><span class="sxs-lookup"><span data-stu-id="999de-124">To load a package:</span></span> 
1. <span data-ttu-id="999de-125">Com um projeto aberto no Visual Studio, **selecione Manage NuGet Packages...** a partir do menu **Projeto.**</span><span class="sxs-lookup"><span data-stu-id="999de-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="999de-126">Clique **em Procurar,** **selecione Inclua pré-relançar** e procure o nome do pacote "Microsoft.Quantum.Nummerics".</span><span class="sxs-lookup"><span data-stu-id="999de-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="999de-127">Isto listará os pacotes disponíveis para download.</span><span class="sxs-lookup"><span data-stu-id="999de-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="999de-128">Passe por cima **da Microsoft.Quantum.Nummerics** e clique na seta de ponta para baixo à direita do número da versão para instalar o pacote numérico.</span><span class="sxs-lookup"><span data-stu-id="999de-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="999de-129">Para mais detalhes, consulte o [guia uI do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-ui)</span><span class="sxs-lookup"><span data-stu-id="999de-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="999de-130">Em alternativa, pode utilizar a Consola Gestor de Pacotes para adicionar a biblioteca numérica ao seu projeto através da interface da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="999de-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Utilize a consola do gestor de pacotes a partir da solicitação de comando](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="999de-132">A partir da consola gestor de pacotes, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="999de-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="999de-133">Para mais detalhes, consulte o guia da [consola do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-console)</span><span class="sxs-lookup"><span data-stu-id="999de-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="999de-134">I Q# Cadernos</span><span class="sxs-lookup"><span data-stu-id="999de-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="999de-135">Pode disponibilizar pacotes adicionais para uso num Bloco de Notas I Q# utilizando o [ `%package` comando mágico.](xref:microsoft.quantum.iqsharp.magic-ref.package)</span><span class="sxs-lookup"><span data-stu-id="999de-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="999de-136">Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para utilização num Bloco de Q# Notas I, executar o seguinte comando numa célula de portátil:</span><span class="sxs-lookup"><span data-stu-id="999de-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="999de-137">Seguindo este comando, o pacote está disponível para quaisquer células dentro do caderno.</span><span class="sxs-lookup"><span data-stu-id="999de-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="999de-138">Para disponibilizar o pacote a partir do Q# código no espaço de trabalho atual, recarregue o espaço de trabalho após a adição do seu pacote:</span><span class="sxs-lookup"><span data-stu-id="999de-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="999de-139">Interoperabilidade da python</span><span class="sxs-lookup"><span data-stu-id="999de-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="999de-140">Você pode disponibilizar pacotes adicionais para uso em um programa de anfitrião Python usando o [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) método.</span><span class="sxs-lookup"><span data-stu-id="999de-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="999de-141">Por exemplo, para adicionar o pacote [**Microsoft.Quantum.Nummerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) para utilização num Q# bloco de notas I, execute o seguinte código Python:</span><span class="sxs-lookup"><span data-stu-id="999de-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="999de-142">Seguindo este comando, o pacote será disponibilizado a qualquer Q# código compilado utilizando `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="999de-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="999de-143">Para disponibilizar o pacote a partir do Q# código no espaço de trabalho atual, recarregue o espaço de trabalho após a adição do seu pacote:</span><span class="sxs-lookup"><span data-stu-id="999de-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
