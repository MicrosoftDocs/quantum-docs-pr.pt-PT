---
title: Introdução à Biblioteca de Química Quântica
description: Saiba mais sobre a Biblioteca de Química Quântica da Microsoft e como é utilizada para simular problemas estruturais eletrónicos em computadores quânticos.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847475"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a>Introdução à Biblioteca de Química Quântica

Desde há muito que a simulação de sistemas físicos tem vindo a desempenhar um papel central na computação quântica.  Tal acontece porque muitos acreditam que a dinâmica quântica é difícil de simular em computadores quânticos, o que significa que a complexidade da simulação do sistema varia exponencialmente em dimensão de acordo com o tamanho do sistema quântico em questão.  A simulação de problemas na química e na ciência material continua a ser, talvez, a aplicação mais evocativa da computação quântica e permitir-nos-ia investigar mecanismos de reação química que até agora estavam além da nossa capacidade de medição ou de simulação.  Também nos permitiria simular materiais eletrónicos correlacionados, como supercondutores a alta temperatura. A lista de aplicações neste espaço é longa.

A finalidade desta documentação é fornecer uma introdução concisa à simulação de problemas da estrutura eletrónica em computadores quânticos para ajudar o leitor a compreender a função que muitos aspetos da biblioteca de simulação Hamiltoniana desempenham no espaço.  Vamos começar com uma breve introdução à mecânica quântica e, em seguida, vamos analisar como os sistemas eletrónicos são modelados.  Posteriormente, vamos abordar como essa dinâmica quântica pode ser emulada com um computador quântico.  Depois de concluída esta parte, vamos falar de dois métodos utilizados para compilar a dinâmica quântica em sequências de portas elementares: decomposições de Trotter-Suzuki e “qubitization”.
