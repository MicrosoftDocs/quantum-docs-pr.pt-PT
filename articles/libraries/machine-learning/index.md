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
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="930cc-103">Introdução à Biblioteca de Machine Learning Quântico</span><span class="sxs-lookup"><span data-stu-id="930cc-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="930cc-104">A Biblioteca de Machine Learning Quântico é uma API, escrita em C#, que lhe permite executar experimentações de machine learning quânticas/clássicas híbridas.</span><span class="sxs-lookup"><span data-stu-id="930cc-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="930cc-105">Com a biblioteca, pode:</span><span class="sxs-lookup"><span data-stu-id="930cc-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="930cc-106">carregar os seus próprios dados para classificação com simuladores quânticos</span><span class="sxs-lookup"><span data-stu-id="930cc-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="930cc-107">utilizar exemplos e tutoriais para ver as introduções ao campo de machine learning quântico.</span><span class="sxs-lookup"><span data-stu-id="930cc-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="930cc-108">Pode esperar um desempenho baixo em comparação com os frameworks de machine learning clássicos atuais (lembre-se de que está tudo a ser executado na simulação de um dispositivo quântico que já é caro em termos de computação).</span><span class="sxs-lookup"><span data-stu-id="930cc-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="930cc-109">O objetivo desta documentação é:</span><span class="sxs-lookup"><span data-stu-id="930cc-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="930cc-110">mostrar uma introdução concisa às ferramentas de machine learning (escritas em Q\#) para aprendizagem quântica/clássica híbrida.</span><span class="sxs-lookup"><span data-stu-id="930cc-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="930cc-111">apresentar os conceitos de machine learning e, mais concretamente, como os criar em classificadores quânticos orientados para circuitos (também conhecidos como classificadores sequenciais quânticos).</span><span class="sxs-lookup"><span data-stu-id="930cc-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="930cc-112">disponibilizar um conjunto de tutoriais de noções básicas para começar a utilizar as ferramentas que a biblioteca fornece.</span><span class="sxs-lookup"><span data-stu-id="930cc-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="930cc-113">debater os métodos de preparação e validação desses classificadores e como se traduzem em operações Q\# específicas fornecidas pela biblioteca.</span><span class="sxs-lookup"><span data-stu-id="930cc-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="930cc-114">O modelo implementado nesta biblioteca tem por base o esquema de preparação quântico-clássico apresentado nos [classificadores quânticos orientados para circuitos](https://arxiv.org/abs/1804.00633)</span><span class="sxs-lookup"><span data-stu-id="930cc-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
