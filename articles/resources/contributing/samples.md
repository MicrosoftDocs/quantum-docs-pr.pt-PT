---
title: Amostras contribuindo para o Microsoft QDK
description: Saiba como contribuir com o código de amostra para o Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275396"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="a7a8f-103">Amostras contribuindo para o Kit de Desenvolvimento Quântico</span><span class="sxs-lookup"><span data-stu-id="a7a8f-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="a7a8f-104">Se está interessado em contribuir com o código para o [repositório de amostras,](https://github.com/Microsoft/Quantum)obrigado por fazer da comunidade de desenvolvimento quântico um lugar melhor!</span><span class="sxs-lookup"><span data-stu-id="a7a8f-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="a7a8f-105">O Kit de Desenvolvimento Quântico mostra repositório</span><span class="sxs-lookup"><span data-stu-id="a7a8f-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="a7a8f-106">Para ajudá-lo a preparar a sua contribuição para ajudar o máximo possível, é útil dar uma olhada rápida na forma como o repositório de amostras está definido:</span><span class="sxs-lookup"><span data-stu-id="a7a8f-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="a7a8f-107">Ou seja, as [amostras do repositório microsoft/Quantum](https://github.com/microsoft/Quantum) são divididas por área temática em diferentes pastas, tais como `algorithms/` , ou `arithmetic/` `characterization/` .</span><span class="sxs-lookup"><span data-stu-id="a7a8f-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="a7a8f-108">Dentro da pasta para cada área de assunto, cada amostra é constituída por uma única pasta que recolhe tudo o que um utilizador precisa para explorar e fazer uso dessa amostra.</span><span class="sxs-lookup"><span data-stu-id="a7a8f-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="a7a8f-109">Como as amostras são estruturadas</span><span class="sxs-lookup"><span data-stu-id="a7a8f-109">How Samples are Structured</span></span>

<span data-ttu-id="a7a8f-110">Olhando para os ficheiros que compõem cada pasta, vamos mergulhar na [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) amostra.</span><span class="sxs-lookup"><span data-stu-id="a7a8f-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="a7a8f-111">Ficheiro</span><span class="sxs-lookup"><span data-stu-id="a7a8f-111">File</span></span>              | <span data-ttu-id="a7a8f-112">Description</span><span class="sxs-lookup"><span data-stu-id="a7a8f-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="a7a8f-113">Projeto Q# usado para construir a amostra com o .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="a7a8f-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="a7a8f-114">Operações e funções Q# para a amostra</span><span class="sxs-lookup"><span data-stu-id="a7a8f-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="a7a8f-115">C# programa de anfitrião usado para executar a amostra</span><span class="sxs-lookup"><span data-stu-id="a7a8f-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="a7a8f-116">Programa de anfitrião python usado para executar a amostra</span><span class="sxs-lookup"><span data-stu-id="a7a8f-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="a7a8f-117">Documentação sobre o que a amostra faz e como usá-la</span><span class="sxs-lookup"><span data-stu-id="a7a8f-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="a7a8f-118">Nem todas as amostras terão exatamente o mesmo conjunto de ficheiros (por exemplo: algumas amostras podem ser C#-only, outras podem não ter um hospedeiro Python, ou algumas amostras podem exigir que os ficheiros de dados auxillary funcionem).</span><span class="sxs-lookup"><span data-stu-id="a7a8f-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="a7a8f-119">Anatomia de um Arquivo README Útil</span><span class="sxs-lookup"><span data-stu-id="a7a8f-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="a7a8f-120">Um ficheiro especialmente importante, no entanto, é o `README.md` ficheiro, já que é isso que os utilizadores precisam para começar com a sua amostra!</span><span class="sxs-lookup"><span data-stu-id="a7a8f-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="a7a8f-121">Cada um `README.md` deve começar com alguns metadados que ajudam docs.microsoft.com/samples encontrar a sua contribuição.</span><span class="sxs-lookup"><span data-stu-id="a7a8f-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a7a8f-122">Veja como a amostra do chsh-game é renderizada</span><span class="sxs-lookup"><span data-stu-id="a7a8f-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="a7a8f-123">Estes metadados são fornecidos como um [cabeçalho YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) que indica quais as línguas que a sua amostra cobre (normalmente, isto será `qsharp` , e ) e quais os produtos que a sua amostra cobre `csharp` `python` (normalmente, `qdk` apenas).</span><span class="sxs-lookup"><span data-stu-id="a7a8f-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="a7a8f-124">A `page_type: sample` chave no cabeçalho é necessária para que a sua amostra apareça em docs.microsoft.com/samples.</span><span class="sxs-lookup"><span data-stu-id="a7a8f-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="a7a8f-125">Da mesma forma, as `product` chaves e as chaves são `language` fundamentais para ajudar os utilizadores a encontrar e executar a sua amostra.</span><span class="sxs-lookup"><span data-stu-id="a7a8f-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="a7a8f-126">Depois disso, é útil dar uma pequena introdução que diga o que a sua nova amostra faz:</span><span class="sxs-lookup"><span data-stu-id="a7a8f-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="a7a8f-127">Os utilizadores da sua amostra também apreciarão saber o que precisam para executá-lo (por exemplo: os utilizadores só precisam do próprio Kit de Desenvolvimento Quântico, ou precisam de software adicional, como node.js?):</span><span class="sxs-lookup"><span data-stu-id="a7a8f-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="a7a8f-128">Com tudo isso no lugar, pode dizer aos utilizadores como executar a sua amostra:</span><span class="sxs-lookup"><span data-stu-id="a7a8f-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="a7a8f-129">Finalmente, é útil dizer aos utilizadores o que cada ficheiro da sua amostra faz, e onde podem ir para mais informações:</span><span class="sxs-lookup"><span data-stu-id="a7a8f-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="a7a8f-130">Certifique-se de que utiliza URLs absolutos aqui, uma vez que a sua amostra aparecerá num URL diferente quando renderizado em docs.microsoft.com/samples!</span><span class="sxs-lookup"><span data-stu-id="a7a8f-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
