---
title: Aplicações de exemplo de química quântica
description: Explore os exemplos de aplicações da biblioteca de química quântica da Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273932"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="6cc38-103">Exemplos de química quântica</span><span class="sxs-lookup"><span data-stu-id="6cc38-103">Quantum chemistry examples</span></span>

<span data-ttu-id="6cc38-104">Nos conceitos de química quântica, criámos manualmente Hamiltonianos de fermiões de exemplo.</span><span class="sxs-lookup"><span data-stu-id="6cc38-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="6cc38-105">Agora, vamos combinar os algoritmos de simulação química descritos em [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) (Simular a dinâmica Hamiltoniana) com [estimativa de fase quântica](xref:microsoft.quantum.libraries.characterization) na biblioteca Canon.</span><span class="sxs-lookup"><span data-stu-id="6cc38-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="6cc38-106">Esta combinação permite-nos obter estimativas de níveis energéticos na molécula representada, que é uma das principais aplicações da química quântica num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="6cc38-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="6cc38-107">Em vez de especificar os termos do Hamiltoniano um a um, também vamos analisar alguns exemplos que nos permitem executar experimentações de química quântica em escala.</span><span class="sxs-lookup"><span data-stu-id="6cc38-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="6cc38-108">Vamos começar com exemplos que carregam um Hamiltoniano de química codificado no [Esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="6cc38-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="6cc38-109">Nas moléculas que são demasiado grandes para simular no [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), continua a ser possível executar ciência interessante.</span><span class="sxs-lookup"><span data-stu-id="6cc38-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="6cc38-110">Por exemplo, os custos dos recursos da execução de grandes simulações químicas continuam a poder ser avaliados ao serem direcionados para o [simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="6cc38-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="6cc38-111">Agora, vamos ilustrar aplicações interessantes da biblioteca de simulação de química através de alguns dos exemplos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="6cc38-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
