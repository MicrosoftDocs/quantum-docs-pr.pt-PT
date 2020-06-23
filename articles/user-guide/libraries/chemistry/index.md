---
title: Introdução à Biblioteca de Química Quântica
description: Saiba mais sobre a Biblioteca de Química Quântica da Microsoft e como é utilizada para simular problemas estruturais eletrónicos em computadores quânticos.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
ms.openlocfilehash: 4268eafa5e53c0a026d179503ac6db88652a8f90
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273684"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introdução à Biblioteca de Química Quântica

Desde há muito que a simulação de sistemas físicos tem vindo a desempenhar um papel central na computação quântica.  Tal acontece porque muitos acreditam que a dinâmica quântica é difícil de simular em computadores quânticos, o que significa que a complexidade da simulação do sistema varia exponencialmente em dimensão de acordo com o tamanho do sistema quântico em questão.  A simulação de problemas na química e na ciência material continua a ser, talvez, a aplicação mais evocativa da computação quântica e permitir-nos-ia investigar mecanismos de reação química que até agora estavam além da nossa capacidade de medição ou de simulação.  Também nos permitiria simular materiais eletrónicos correlacionados, como supercondutores a alta temperatura. A lista de aplicações neste espaço é longa.

A finalidade desta documentação é fornecer uma introdução concisa à simulação de problemas da estrutura eletrónica em computadores quânticos para ajudar o leitor a compreender a função que muitos aspetos da biblioteca de simulação Hamiltoniana desempenham no espaço.  Vamos começar com uma breve introdução à mecânica quântica e, em seguida, vamos analisar como os sistemas eletrónicos são modelados.  Posteriormente, vamos abordar como essa dinâmica quântica pode ser emulada com um computador quântico.  Depois de concluída esta parte, vamos falar de dois métodos utilizados para compilar a dinâmica quântica em sequências de portas elementares: decomposições de Trotter-Suzuki e “qubitization”.
