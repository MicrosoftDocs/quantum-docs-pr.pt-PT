---
title: Bibliotecas do Quantum Development kit
description: Descrição geral das bibliotecas padrão, de química e numéricas incluídas no Microsoft Quantum Development kit.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 90672b6ec78bf8305bdb3ab8326002cf8ce34bfe
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835728"
---
# <a name="overview-of-no-locq-libraries"></a><span data-ttu-id="9fcbd-103">Descrição geral das Bibliotecas Q#</span><span class="sxs-lookup"><span data-stu-id="9fcbd-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="9fcbd-104">O Quantum Development Kit é fornecido com várias bibliotecas para facilitar o desenvolvimento de aplicações quânticas em Q#.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="9fcbd-105">Nesta seção da documentação, vamos descrever estas bibliotecas e como as pode utilizar nos seus programas.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="9fcbd-106">[**Bibliotecas padrão**](xref:microsoft.quantum.libraries.standard.intro): esta seção descreve o prelúdio, que define a interface entre os programas Q# e computadores de destino e a Canon, uma biblioteca Q# que fornece operações e funções para fins gerais para utilização na escrita de programas de Q#.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="9fcbd-107">[**Biblioteca de química quântica**](xref:microsoft.quantum.chemistry.concepts.intro): esta seção descreve a biblioteca de química quântica, que fornece um modelo de dados para carregar representações de Hamiltonianos fermiónicos e operações e funções de simulação quântica que agem sobre estas representações.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="9fcbd-108">[**Biblioteca numérica quântica**](xref:microsoft.quantum.numerics.intro): esta seção descreve a biblioteca numérica quântica, que fornece implementações para um anfitrião de funções matemáticas.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="9fcbd-109">Suporta números inteiros (assinados e não assinados) e representações de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="9fcbd-110">[**Biblioteca de machine learning quântica**](xref:microsoft.quantum.machine-learning.concepts.intro): Esta secção descreve a biblioteca de machine learning quântico, que fornece uma implementação dos classificadores sequenciais que tiram partido da computação quântica para compreender os dados.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="9fcbd-111">Podem obter no GitHub as origens das bibliotecas e exemplos de código.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="9fcbd-112">Para obter mais informações, veja [Licenciamento](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="9fcbd-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="9fcbd-113">Tenha em conta que também estão disponíveis referências de pacotes ("binários") para as bibliotecas, que oferecem outra forma de as incluir em projetos.</span><span class="sxs-lookup"><span data-stu-id="9fcbd-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="9fcbd-114">Uma maneira fácil de as obter é através do [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="9fcbd-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
