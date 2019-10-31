---
title: Exemplos de química quântica | Microsoft Docs
description: Exemplos de química quântica – Docs
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 586ea98321ff71947df8d81a2141a8b050dbd9ed
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960406"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="8343b-103">Exemplos de química quântica</span><span class="sxs-lookup"><span data-stu-id="8343b-103">Quantum chemistry examples</span></span>

<span data-ttu-id="8343b-104">Nos conceitos de química quântica, criámos manualmente Hamiltonianos de fermiões de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8343b-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="8343b-105">Agora, vamos combinar os algoritmos de simulação química descritos em [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) (Simular a dinâmica Hamiltoniana) com [estimativa de fase quântica](xref:microsoft.quantum.libraries.characterization) na biblioteca Canon.</span><span class="sxs-lookup"><span data-stu-id="8343b-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="8343b-106">Esta combinação permite-nos obter estimativas de níveis energéticos na molécula representada, que é uma das principais aplicações da química quântica num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="8343b-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="8343b-107">Em vez de especificar os termos do Hamiltoniano um a um, também vamos analisar alguns exemplos que nos permitem executar experimentações de química quântica em escala.</span><span class="sxs-lookup"><span data-stu-id="8343b-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="8343b-108">Vamos começar com exemplos que carregam um Hamiltoniano de química codificado no [Esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="8343b-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="8343b-109">Nas moléculas que são demasiado grandes para simular no [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), continua a ser possível executar ciência interessante.</span><span class="sxs-lookup"><span data-stu-id="8343b-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="8343b-110">Por exemplo, os custos dos recursos da execução de grandes simulações químicas continuam a poder ser avaliados ao serem direcionados para o [simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="8343b-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="8343b-111">Agora, vamos ilustrar aplicações interessantes da biblioteca de simulação de química através de alguns dos exemplos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="8343b-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>