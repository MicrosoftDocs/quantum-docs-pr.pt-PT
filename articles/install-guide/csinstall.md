---
title: Programar com Q# + C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680169"
---
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="1fcc0-102">Usando Q#\# com C e F\#</span><span class="sxs-lookup"><span data-stu-id="1fcc0-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="1fcc0-103">Q# é construído para jogar bem com .NET línguas como C# e F#.</span><span class="sxs-lookup"><span data-stu-id="1fcc0-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="1fcc0-104">Neste guia, vamos demonstrar como usar o Q# com um programa de anfitriões escrito numa linguagem .NET.</span><span class="sxs-lookup"><span data-stu-id="1fcc0-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1fcc0-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1fcc0-105">Prerequisites</span></span>

- <span data-ttu-id="1fcc0-106">Instale o Kit de Desenvolvimento Quântico [para utilização com projetos de linha de comando Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="1fcc0-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="1fcc0-107">Criar uma biblioteca Q# e um hospedeiro .NET</span><span class="sxs-lookup"><span data-stu-id="1fcc0-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="1fcc0-108">O primeiro passo é criar projetos para a sua biblioteca Q# e para o anfitrião .NET que irá chamar para as operações e funções definidas na sua biblioteca Q#.</span><span class="sxs-lookup"><span data-stu-id="1fcc0-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="1fcc0-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="1fcc0-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="1fcc0-110">Criar uma nova biblioteca Q#</span><span class="sxs-lookup"><span data-stu-id="1fcc0-110">Create a new Q# library</span></span>
  - <span data-ttu-id="1fcc0-111">Ir para **Arquivar** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="1fcc0-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="1fcc0-112">Digite "Q#" na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="1fcc0-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="1fcc0-113">Selecione **Biblioteca Q#**</span><span class="sxs-lookup"><span data-stu-id="1fcc0-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="1fcc0-114">Selecione **Next**</span><span class="sxs-lookup"><span data-stu-id="1fcc0-114">Select **Next**</span></span>
  - <span data-ttu-id="1fcc0-115">Escolha um nome e localização para a sua biblioteca</span><span class="sxs-lookup"><span data-stu-id="1fcc0-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="1fcc0-116">Certifique-se de que "colocar projeto e solução no mesmo diretório" não é **verificado**</span><span class="sxs-lookup"><span data-stu-id="1fcc0-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="1fcc0-117">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="1fcc0-117">Select **Create**</span></span>
- <span data-ttu-id="1fcc0-118">Crie um novo programa de anfitriões C# ou F#</span><span class="sxs-lookup"><span data-stu-id="1fcc0-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="1fcc0-119">Ir a **Arquivo** → **Novo** **Projeto** →</span><span class="sxs-lookup"><span data-stu-id="1fcc0-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="1fcc0-120">Selecione "Console App (.NET Core")" para C# ou F #</span><span class="sxs-lookup"><span data-stu-id="1fcc0-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="1fcc0-121">Selecione **Next**</span><span class="sxs-lookup"><span data-stu-id="1fcc0-121">Select **Next**</span></span>
  - <span data-ttu-id="1fcc0-122">Sob *solução*, selecione "adicionar à solução"</span><span class="sxs-lookup"><span data-stu-id="1fcc0-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="1fcc0-123">Escolha um nome para o seu programa de anfitriões</span><span class="sxs-lookup"><span data-stu-id="1fcc0-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="1fcc0-124">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="1fcc0-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="1fcc0-125">Código de estúdio visual ou linha de comando</span><span class="sxs-lookup"><span data-stu-id="1fcc0-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="1fcc0-126">Criar uma nova biblioteca Q#</span><span class="sxs-lookup"><span data-stu-id="1fcc0-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="1fcc0-127">Criar um novo projeto de consola C# ou F#</span><span class="sxs-lookup"><span data-stu-id="1fcc0-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="1fcc0-128">Adicione a sua biblioteca Q# como referência do seu programa de anfitriões</span><span class="sxs-lookup"><span data-stu-id="1fcc0-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="1fcc0-129">[Opcional] Criar uma solução para ambos os projetos</span><span class="sxs-lookup"><span data-stu-id="1fcc0-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="1fcc0-130">Chamando para Q# de .NET</span><span class="sxs-lookup"><span data-stu-id="1fcc0-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="1fcc0-131">Assim que tiver os seus projetos configurados seguindo as instruções acima, pode ligar para Q# a partir da sua aplicação de consola .NET.</span><span class="sxs-lookup"><span data-stu-id="1fcc0-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="1fcc0-132">O compilador Q# criará classes .NET para cada operação e função Q# que lhe permitem executar os seus programas quânticos num simulador.</span><span class="sxs-lookup"><span data-stu-id="1fcc0-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="1fcc0-133">Por exemplo, a [amostra de interoperabilidade .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) inclui o seguinte exemplo de uma operação Q#:</span><span class="sxs-lookup"><span data-stu-id="1fcc0-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="1fcc0-134">Para chamar esta operação de .NET num simulador `Run` quântico, `RunAlgorithm` pode utilizar o método da classe .NET gerado pelo compilador Q#:</span><span class="sxs-lookup"><span data-stu-id="1fcc0-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="1fcc0-135">C #</span><span class="sxs-lookup"><span data-stu-id="1fcc0-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="1fcc0-136">F#</span><span class="sxs-lookup"><span data-stu-id="1fcc0-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="1fcc0-137">Passos seguintes?</span><span class="sxs-lookup"><span data-stu-id="1fcc0-137">What's next?</span></span>

<span data-ttu-id="1fcc0-138">Agora que tem o Quantum Development Kit configurado para ambos os programas de linha de comando Q# e para interoperabilidade com .NET, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="1fcc0-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
