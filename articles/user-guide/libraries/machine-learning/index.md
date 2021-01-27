---
title: Introdução ao Pacote de Machine Learning Quântico | Microsoft Docs
description: Introdução ao Pacote de Machine Learning Quântico
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: conceptual
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e36948a216a06d76b99cd451bbfac6f5defd7c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858782"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Introdução à Biblioteca de Machine Learning Quântico

A Biblioteca de Machine Learning Quântico é uma API, escrita em Q#, que lhe permite executar experimentações de machine learning quânticas/clássicas híbridas. Com a biblioteca, pode:

- carregar os seus próprios dados para classificação com simuladores quânticos

- utilizar exemplos e tutoriais para ver as introduções ao campo de machine learning quântico.

Pode esperar um desempenho baixo em comparação com os frameworks de machine learning clássicos atuais (lembre-se de que está tudo a ser executado na simulação de um dispositivo quântico que já é caro em termos de computação).

O objetivo desta documentação é:

- mostrar uma introdução concisa às ferramentas de machine learning (escritas em Q\#) para aprendizagem quântica/clássica híbrida.
- apresentar os conceitos de machine learning e, mais concretamente, como os criar em classificadores quânticos orientados para circuitos (também conhecidos como classificadores sequenciais quânticos).
- disponibilizar um conjunto de tutoriais de noções básicas para começar a utilizar as ferramentas que a biblioteca fornece.
- debater os métodos de preparação e validação desses classificadores e como se traduzem em operações Q\# específicas fornecidas pela biblioteca.

O modelo implementado nesta biblioteca tem por base o esquema de preparação quântico-clássico apresentado nos [classificadores quânticos orientados para circuitos](https://arxiv.org/abs/1804.00633)
