---
title: Biblioteca de numéricos Quânticos da Microsoft - Instalação e Validação
description: Saiba como adicionar a biblioteca de numéricos Microsoft Quantum ao seu Visual Studio 2019 ou posterior instalação.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276127"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="f8051-103">Instalação e Validação da Biblioteca Numérica</span><span class="sxs-lookup"><span data-stu-id="f8051-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="f8051-104">O Kit de Desenvolvimento Quântico fornece suporte para a funcionalidade numérica através do [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="f8051-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="f8051-105">**>do Estúdio Visual =2019:** Se estiver a utilizar o Visual Studio 2019 ou mais tarde, pode adicionar o pacote numérico utilizando o NuGet Package Manager.</span><span class="sxs-lookup"><span data-stu-id="f8051-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="f8051-106">Para tal, selecione "Gerir pacotes NuGet..." do item do menu "Project" no Estúdio Visual.</span><span class="sxs-lookup"><span data-stu-id="f8051-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="f8051-107">A partir do separador Browse, procure o nome do pacote "Microsoft.Quantum.Nummerics"</span><span class="sxs-lookup"><span data-stu-id="f8051-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="f8051-108">Certifique-se de marcar "Incluir pré-relançar"</span><span class="sxs-lookup"><span data-stu-id="f8051-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="f8051-109">Isto listará os pacotes disponíveis para download.</span><span class="sxs-lookup"><span data-stu-id="f8051-109">This will list the packages available for download.</span></span>
<span data-ttu-id="f8051-110">Pairar sobre "Microsoft.Quantum.Nummerics" revela uma seta virada para baixo para a direita do número da versão.</span><span class="sxs-lookup"><span data-stu-id="f8051-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="f8051-111">Clique na seta para instalar o pacote numérico.</span><span class="sxs-lookup"><span data-stu-id="f8051-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="f8051-112">Para mais detalhes, consulte o [guia uI do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-ui)</span><span class="sxs-lookup"><span data-stu-id="f8051-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="f8051-113">Em alternativa, pode utilizar a Consola Gestor de Pacotes para adicionar a biblioteca numérica ao seu projeto através da interface da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f8051-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Utilize a consola do gestor de pacotes a partir da linha de comando](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="f8051-115">A partir da consola do gestor de pacotes, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f8051-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="f8051-116">Para mais detalhes, consulte o guia da [consola do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-console)</span><span class="sxs-lookup"><span data-stu-id="f8051-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="f8051-117">**Linha de comando ou Código do Estúdio Visual:** Utilizando a linha de comando por si só ou a partir do Código do Estúdio Visual, pode utilizar o `dotnet` comando para adicionar referência ao pacote NuGet ao seu projeto:</span><span class="sxs-lookup"><span data-stu-id="f8051-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="f8051-118">Verificação da sua instalação</span><span class="sxs-lookup"><span data-stu-id="f8051-118">Verifying your installation</span></span>

<span data-ttu-id="f8051-119">Como o resto do Kit de Desenvolvimento Quântico, a biblioteca numérica vem com amostras que ajudam a começar o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="f8051-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="f8051-120">Para testar a sua instalação utilizando estas amostras, clone o [repositório principal](https://github.com/Microsoft/Quantum) de amostras e, em seguida, execute uma das amostras.</span><span class="sxs-lookup"><span data-stu-id="f8051-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="f8051-121">Para executar a [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) amostra:</span><span class="sxs-lookup"><span data-stu-id="f8051-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
