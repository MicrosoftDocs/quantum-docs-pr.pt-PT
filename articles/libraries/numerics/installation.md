---
title: Biblioteca de numéricos Quânticos da Microsoft - Instalação e Validação
description: Saiba como adicionar a biblioteca de numéricos Da Microsoft Quantum ao seu Visual Studio 2019 ou posterior instalação.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: cb0d00a509b3986b605dd7f15f9bccc0661bb894
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906343"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="f2b7d-103">Instalação e Validação da Biblioteca Numérica</span><span class="sxs-lookup"><span data-stu-id="f2b7d-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="f2b7d-104">O Kit de Desenvolvimento Quântico fornece suporte para a funcionalidade numérica através do pacote [NuGet`Microsoft.Quantum.Numerics`.](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f2b7d-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="f2b7d-105">**Estúdio Visual >=2019:** Se estiver a utilizar o Visual Studio 2019 ou mais tarde, pode adicionar o pacote numérico utilizando o NuGet Package Manager.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="f2b7d-106">Para isso, selecione "Gerir pacotes NuGet..." do item do menu "Project" no Estúdio Visual.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="f2b7d-107">A partir do separador Browse, procure o nome de pacote "Microsoft.Quantum.Numerics"</span><span class="sxs-lookup"><span data-stu-id="f2b7d-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="f2b7d-108">Certifique-se de marcar "Incluir pré-lançamento"</span><span class="sxs-lookup"><span data-stu-id="f2b7d-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="f2b7d-109">Isto listará os pacotes disponíveis para download.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-109">This will list the packages available for download.</span></span>
<span data-ttu-id="f2b7d-110">Pairando sobre "Microsoft.Quantum.Numerics" revela uma seta virada para baixo para a direita do número da versão.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="f2b7d-111">Clique na seta para instalar o pacote numérico.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="f2b7d-112">Para mais detalhes, consulte o [guia UI do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-ui)de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="f2b7d-113">Em alternativa, pode utilizar a Consola gestora de pacotes para adicionar a biblioteca numérica ao seu projeto através da interface da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Utilize a consola gestora de pacotes a partir da linha de comando](../../media/vs2017-nuget-console-menu.png)

<span data-ttu-id="f2b7d-115">A partir da consola gestora de pacotes, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f2b7d-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="f2b7d-116">Para mais detalhes, consulte o guia de [consolas do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-console)de Pacotes .</span><span class="sxs-lookup"><span data-stu-id="f2b7d-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="f2b7d-117">**Linha de comando ou Código** de Estúdio Visual: Utilizando a linha de comando por si só ou dentro do Código visual do Estúdio, pode utilizar o comando `dotnet` para adicionar referência ao pacote NuGet ao seu projeto:</span><span class="sxs-lookup"><span data-stu-id="f2b7d-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="f2b7d-118">Verificar a sua instalação</span><span class="sxs-lookup"><span data-stu-id="f2b7d-118">Verifying your installation</span></span>

<span data-ttu-id="f2b7d-119">Como o resto do Kit de Desenvolvimento Quântico, a biblioteca numérica vem com amostras que o ajudam a começar o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="f2b7d-120">Para testar a sua instalação utilizando estas amostras, clone o [repositório de amostras principais](https://github.com/Microsoft/Quantum) e, em seguida, executar uma das amostras.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="f2b7d-121">Para executar a amostra [`CustomModAdd`:](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd)</span><span class="sxs-lookup"><span data-stu-id="f2b7d-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
