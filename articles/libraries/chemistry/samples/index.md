---
title: Aplicações de exemplo de química quântica
description: Explore os exemplos de aplicações da biblioteca de química quântica da Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906496"
---
# <a name="quantum-chemistry-examples"></a>Exemplos de química quântica

Nos conceitos de química quântica, criámos manualmente Hamiltonianos de fermiões de exemplo. Agora, vamos combinar os algoritmos de simulação química descritos em [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) (Simular a dinâmica Hamiltoniana) com [estimativa de fase quântica](xref:microsoft.quantum.libraries.characterization) na biblioteca Canon. Esta combinação permite-nos obter estimativas de níveis energéticos na molécula representada, que é uma das principais aplicações da química quântica num computador quântico. 

Em vez de especificar os termos do Hamiltoniano um a um, também vamos analisar alguns exemplos que nos permitem executar experimentações de química quântica em escala. Vamos começar com exemplos que carregam um Hamiltoniano de química codificado no [Esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Nas moléculas que são demasiado grandes para simular no [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), continua a ser possível executar ciência interessante. Por exemplo, os custos dos recursos da execução de grandes simulações químicas continuam a poder ser avaliados ao serem direcionados para o [simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Agora, vamos ilustrar aplicações interessantes da biblioteca de simulação de química através de alguns dos exemplos fornecidos.
