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
# <a name="quantum-chemistry-examples"></a>Exemplos de química quântica

Nos conceitos de química quântica, criámos manualmente Hamiltonianos de fermiões de exemplo. Agora, vamos combinar os algoritmos de simulação química descritos em [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) (Simular a dinâmica Hamiltoniana) com [estimativa de fase quântica](xref:microsoft.quantum.libraries.characterization) na biblioteca Canon. Esta combinação permite-nos obter estimativas de níveis energéticos na molécula representada, que é uma das principais aplicações da química quântica num computador quântico. 

Em vez de especificar os termos do Hamiltoniano um a um, também vamos analisar alguns exemplos que nos permitem executar experimentações de química quântica em escala. Vamos começar com exemplos que carregam um Hamiltoniano de química codificado no [Esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Nas moléculas que são demasiado grandes para simular no [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), continua a ser possível executar ciência interessante. Por exemplo, os custos dos recursos da execução de grandes simulações químicas continuam a poder ser avaliados ao serem direcionados para o [simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Agora, vamos ilustrar aplicações interessantes da biblioteca de simulação de química através de alguns dos exemplos fornecidos.