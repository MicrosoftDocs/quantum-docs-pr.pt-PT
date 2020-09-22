---
title: Introdução às bibliotecas padrão Q# da Microsoft
description: Saiba mais sobre as bibliotecas padrão Q# da Microsoft que definam as operações, as funções e os tipos de dados que são utilizados em programas quânticos.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 63709015a12a7f972a676018970143ca163e92d0
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836017"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="fb9b5-103">Introdução às Bibliotecas Padrão Q#</span><span class="sxs-lookup"><span data-stu-id="fb9b5-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="fb9b5-104">A linguagem Q# é suportada por uma série de diferentes operações, funções e tipos definidos pelo utilizador úteis que constituem as *bibliotecas padrão* Q#.</span><span class="sxs-lookup"><span data-stu-id="fb9b5-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="fb9b5-105">O [pacote NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) instalado durante a [instalação e validação](xref:microsoft.quantum.install) fornece o compilador Q# e partes da biblioteca padrão que são implementadas pelos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="fb9b5-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="fb9b5-106">O [pacote `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) fornece a parte das bibliotecas padrão Q# que são portáteis entre computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="fb9b5-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="fb9b5-107">Os símbolos definidos pelas bibliotecas padrão Q# são definidos com detalhes muito maiores e mais completos na [documentação da API](xref:microsoft.quantum.apiref-intro).</span><span class="sxs-lookup"><span data-stu-id="fb9b5-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.apiref-intro).</span></span>

<span data-ttu-id="fb9b5-108">Nas secções seguintes, vamos descrever as funcionalidades mais relevantes de cada parte da biblioteca padrão e fornecer contexto sobre como cada funcionalidade pode ser utilizada na prática.</span><span class="sxs-lookup"><span data-stu-id="fb9b5-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
