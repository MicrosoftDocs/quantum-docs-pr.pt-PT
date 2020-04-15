---
title: Introdução ao Pacote de Machine Learning Quântico | Microsoft Docs
description: Introdução ao Pacote de Machine Learning Quântico
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907856"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Introdução à Biblioteca de Machine Learning Quântico

A Biblioteca de Machine Learning Quântico é uma API, escrita em C#, que lhe permite executar experimentações de machine learning quânticas/clássicas híbridas. Com a biblioteca, pode:

- carregar os seus próprios dados para classificação com simuladores quânticos

- utilizar exemplos e tutoriais para ver as introduções ao campo de machine learning quântico.

Pode esperar um desempenho baixo em comparação com os frameworks de machine learning clássicos atuais (lembre-se de que está tudo a ser executado na simulação de um dispositivo quântico que já é caro em termos de computação).

O objetivo desta documentação é:

- mostrar uma introdução concisa às ferramentas de machine learning (escritas em Q\#) para aprendizagem quântica/clássica híbrida.
- apresentar os conceitos de machine learning e, mais concretamente, como os criar em classificadores quânticos orientados para circuitos (também conhecidos como classificadores sequenciais quânticos).
- disponibilizar um conjunto de tutoriais de noções básicas para começar a utilizar as ferramentas que a biblioteca fornece.
- debater os métodos de preparação e validação desses classificadores e como se traduzem em operações Q\# específicas fornecidas pela biblioteca.

O modelo implementado nesta biblioteca tem por base o esquema de preparação quântico-clássico apresentado nos [classificadores quânticos orientados para circuitos](https://arxiv.org/abs/1804.00633)
