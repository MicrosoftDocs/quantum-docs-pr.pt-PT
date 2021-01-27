---
title: Desenvolver com Q# e .NET
description: Saiba como criar uma aplicação Q# com linguagens .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: de79c361331766572f5608c341be766e071e01b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844310"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="b8411-103">Desenvolver com Q# e .NET</span><span class="sxs-lookup"><span data-stu-id="b8411-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="b8411-104">O Q# foi criado para funcionar bem com linguagens .NET, como C# e F#.</span><span class="sxs-lookup"><span data-stu-id="b8411-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="b8411-105">Neste guia, vamos demonstrar como utilizar o Q# com um programa anfitrião escrito numa linguagem .NET.</span><span class="sxs-lookup"><span data-stu-id="b8411-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="b8411-106">Primeiro, vamos criar a aplicação Q# e o anfitrião .NET e, em seguida, demonstrar como chamar para Q# a partir do anfitrião.</span><span class="sxs-lookup"><span data-stu-id="b8411-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8411-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b8411-107">Prerequisites</span></span>

- <span data-ttu-id="b8411-108">Instale o Quantum Development Kit [para utilização com projetosQ#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="b8411-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="b8411-109">Criar uma biblioteca Q# e um anfitrião .NET</span><span class="sxs-lookup"><span data-stu-id="b8411-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="b8411-110">O primeiro passo é criar projetos para a biblioteca Q# e para o anfitrião .NET que vai chamar as operações e as funções definidas na biblioteca Q#.</span><span class="sxs-lookup"><span data-stu-id="b8411-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="b8411-111">Siga as instruções no separador correspondente ao seu ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="b8411-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="b8411-112">Se estiver a utilizar um editor que não seja o Visual Studio ou o VS Code, basta seguir os passos da linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="b8411-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="b8411-113">Visual Studio Code ou linha de comandos</span><span class="sxs-lookup"><span data-stu-id="b8411-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="b8411-114">Criar uma nova biblioteca Q#</span><span class="sxs-lookup"><span data-stu-id="b8411-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="b8411-115">Criar um projeto de consola C# ou F# novo</span><span class="sxs-lookup"><span data-stu-id="b8411-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="b8411-116">Adicionar a biblioteca Q# como referência a partir do programa anfitrião</span><span class="sxs-lookup"><span data-stu-id="b8411-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="b8411-117">[Opcional] Criar uma solução para ambos os projetos</span><span class="sxs-lookup"><span data-stu-id="b8411-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="b8411-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b8411-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="b8411-119">Criar uma nova biblioteca Q#</span><span class="sxs-lookup"><span data-stu-id="b8411-119">Create a new Q# library</span></span>
  - <span data-ttu-id="b8411-120">Aceda a **Ficheiro** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="b8411-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="b8411-121">Escreva "Q#" na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="b8411-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="b8411-122">Selecione **Biblioteca Q#**</span><span class="sxs-lookup"><span data-stu-id="b8411-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="b8411-123">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="b8411-123">Select **Next**</span></span>
  - <span data-ttu-id="b8411-124">Escolha um nome e uma localização para a biblioteca</span><span class="sxs-lookup"><span data-stu-id="b8411-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="b8411-125">Confirme que "place project and solution in same directory" ("pôr projeto e solução no mesmo diretório") está **desmarcado**</span><span class="sxs-lookup"><span data-stu-id="b8411-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="b8411-126">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="b8411-126">Select **Create**</span></span>
- <span data-ttu-id="b8411-127">Criar um programa anfitrião C# ou F# novo</span><span class="sxs-lookup"><span data-stu-id="b8411-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="b8411-128">Aceda a **File** (Ficheiro) → **New** (Novo) → **Project** (Projeto)</span><span class="sxs-lookup"><span data-stu-id="b8411-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="b8411-129">Selecione "Console App (.NET Core")" ("Aplicação de Consola (.NET Core")" para C# ou F#</span><span class="sxs-lookup"><span data-stu-id="b8411-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="b8411-130">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="b8411-130">Select **Next**</span></span>
  - <span data-ttu-id="b8411-131">Em *solution* (solução), selecione "add to solution" ("adicionar à solução")</span><span class="sxs-lookup"><span data-stu-id="b8411-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="b8411-132">Escolha um nome para o programa anfitrião</span><span class="sxs-lookup"><span data-stu-id="b8411-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="b8411-133">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="b8411-133">Select **Create**</span></span>

<span data-ttu-id="b8411-134">\*\*_</span><span class="sxs-lookup"><span data-stu-id="b8411-134">\*\*_</span></span>

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="b8411-135">Chamar o Q# a partir de .NET</span><span class="sxs-lookup"><span data-stu-id="b8411-135">Calling into Q# from .NET</span></span>

<span data-ttu-id="b8411-136">Quando os projetos estiverem configurados de acordo com as instruções acima, pode chamar o Q# a partir da aplicação de consola .NET.</span><span class="sxs-lookup"><span data-stu-id="b8411-136">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="b8411-137">O compilador Q# vai criar classes .NET para cada operação e função Q# que lhe permitem executar os seus programas quânticos num simulador.</span><span class="sxs-lookup"><span data-stu-id="b8411-137">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="b8411-138">Por exemplo, a [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) inclui o seguinte exemplo de uma operação Q#:</span><span class="sxs-lookup"><span data-stu-id="b8411-138">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="b8411-139">Para chamar esta operação a partir de .NET num simulador quântico, pode utilizar o método `Run` da classe `RunAlgorithm` .NET gerado pelo compilador Q#:</span><span class="sxs-lookup"><span data-stu-id="b8411-139">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="b8411-140">C#</span><span class="sxs-lookup"><span data-stu-id="b8411-140">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="b8411-141">F#</span><span class="sxs-lookup"><span data-stu-id="b8411-141">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

<span data-ttu-id="b8411-142">_\*\*</span><span class="sxs-lookup"><span data-stu-id="b8411-142">_\*\*</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="b8411-143">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="b8411-143">Next steps</span></span>

<span data-ttu-id="b8411-144">Agora que o Quantum Development Kit está configurado para aplicações Q# e para interoperabilidade com o .NET, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="b8411-144">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
