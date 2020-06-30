---
title: Desenvolver com Q# e .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274153"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="73675-102">Desenvolver com Q# e .NET</span><span class="sxs-lookup"><span data-stu-id="73675-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="73675-103">O Q# foi criado para funcionar bem com linguagens .NET, como C# e F#.</span><span class="sxs-lookup"><span data-stu-id="73675-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="73675-104">Neste guia, vamos demonstrar como utilizar o Q# com um programa anfitrião escrito numa linguagem .NET.</span><span class="sxs-lookup"><span data-stu-id="73675-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73675-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="73675-105">Prerequisites</span></span>

- <span data-ttu-id="73675-106">Instale o Quantum Development kit [para utilização com projetos de linha de comandos Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="73675-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="73675-107">Criar uma biblioteca de Q# e um anfitrião .NET</span><span class="sxs-lookup"><span data-stu-id="73675-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="73675-108">O primeiro passo é criar projetos para a biblioteca de Q# e para o anfitrião .NET que vai chamar as operações e as funções definidas na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="73675-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="73675-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="73675-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="73675-110">Criar uma biblioteca de Q# nova</span><span class="sxs-lookup"><span data-stu-id="73675-110">Create a new Q# library</span></span>
  - <span data-ttu-id="73675-111">Aceda a **Ficheiro** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="73675-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="73675-112">Escreva "Q#" na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="73675-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="73675-113">Selecione **Q# Library** (Biblioteca de Q#)</span><span class="sxs-lookup"><span data-stu-id="73675-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="73675-114">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="73675-114">Select **Next**</span></span>
  - <span data-ttu-id="73675-115">Escolha um nome e uma localização para a biblioteca</span><span class="sxs-lookup"><span data-stu-id="73675-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="73675-116">Confirme que "place project and solution in same directory" ("pôr projeto e solução no mesmo diretório") está **desmarcado**</span><span class="sxs-lookup"><span data-stu-id="73675-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="73675-117">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="73675-117">Select **Create**</span></span>
- <span data-ttu-id="73675-118">Criar um programa anfitrião C# ou F# novo</span><span class="sxs-lookup"><span data-stu-id="73675-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="73675-119">Aceda a **File** (Ficheiro) → **New** (Novo) → **Project** (Projeto)</span><span class="sxs-lookup"><span data-stu-id="73675-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="73675-120">Selecione "Console App (.NET Core")" ("Aplicação de Consola (.NET Core")" para C# ou F#</span><span class="sxs-lookup"><span data-stu-id="73675-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="73675-121">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="73675-121">Select **Next**</span></span>
  - <span data-ttu-id="73675-122">Em *solution* (solução), selecione "add to solution" ("adicionar à solução")</span><span class="sxs-lookup"><span data-stu-id="73675-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="73675-123">Escolha um nome para o programa anfitrião</span><span class="sxs-lookup"><span data-stu-id="73675-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="73675-124">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="73675-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="73675-125">Visual Studio Code ou Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="73675-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="73675-126">Criar uma biblioteca de Q# nova</span><span class="sxs-lookup"><span data-stu-id="73675-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="73675-127">Criar um projeto de consola C# ou F# novo</span><span class="sxs-lookup"><span data-stu-id="73675-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="73675-128">Adicionar a biblioteca de Q# como referência a partir do programa anfitrião</span><span class="sxs-lookup"><span data-stu-id="73675-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="73675-129">[Opcional] Criar uma solução para ambos os projetos</span><span class="sxs-lookup"><span data-stu-id="73675-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="73675-130">Chamar o Q# a partir de .NET</span><span class="sxs-lookup"><span data-stu-id="73675-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="73675-131">Quando os projetos estiverem configurados de acordo com as instruções acima, pode chamar o Q# a partir da aplicação de consola .NET.</span><span class="sxs-lookup"><span data-stu-id="73675-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="73675-132">O compilador Q# vai criar classes .NET para cada operação e função Q# que lhe permitem executar os seus programas quânticos num simulador.</span><span class="sxs-lookup"><span data-stu-id="73675-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="73675-133">Por exemplo, a [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) inclui o seguinte exemplo de uma operação Q#:</span><span class="sxs-lookup"><span data-stu-id="73675-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="73675-134">Para chamar esta operação a partir de .NET num simulador quântico, pode utilizar o método `Run` da classe `RunAlgorithm` .NET gerado pelo compilador Q#:</span><span class="sxs-lookup"><span data-stu-id="73675-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="73675-135">C#</span><span class="sxs-lookup"><span data-stu-id="73675-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="73675-136">F#</span><span class="sxs-lookup"><span data-stu-id="73675-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="73675-137">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="73675-137">Next steps</span></span>

<span data-ttu-id="73675-138">Agora que o Quantum Development Kit está configurado para programas de linha de comandos Q# e para interoperabilidade com .NET, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="73675-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
