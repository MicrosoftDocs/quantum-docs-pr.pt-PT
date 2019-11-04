---
title: A Linguagem de Programação Q# | Microsoft Docs
description: A Linguagem de Programação Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: 560926f6f3e05c32a935f01ca5107a614e743ee2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442479"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="b0c45-103">A Linguagem de Programação Q#</span><span class="sxs-lookup"><span data-stu-id="b0c45-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="b0c45-104">Introdução</span><span class="sxs-lookup"><span data-stu-id="b0c45-104">Introduction</span></span>

<span data-ttu-id="b0c45-105">Um modelo natural de computação quântica é tratar o computador quântico como coprocessador, semelhante ao que é utilizado em GPUs, FPGAs e outros processadores adjuntos.</span><span class="sxs-lookup"><span data-stu-id="b0c45-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="b0c45-106">A lógica de controlo primária executa código clássico num computador “anfitrião” clássico.</span><span class="sxs-lookup"><span data-stu-id="b0c45-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="b0c45-107">Quando for pertinente e necessário, o programa anfitrião pode invocar uma sub-rotina que é executada no processador adjunto.</span><span class="sxs-lookup"><span data-stu-id="b0c45-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="b0c45-108">Quando a sub-rotina for concluída, o programa anfitrião obtém acesso aos resultados da mesma.</span><span class="sxs-lookup"><span data-stu-id="b0c45-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="b0c45-109">Q# (Q-Sharp) é uma linguagem de programação específica de domínio, utilizada para expressar algoritmos quânticos.</span><span class="sxs-lookup"><span data-stu-id="b0c45-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="b0c45-110">É utilizada para escrever sub-rotinas que são executadas num processador quântico adjunto, sob o controlo de um computador e programa anfitrião clássico.</span><span class="sxs-lookup"><span data-stu-id="b0c45-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="b0c45-111">Até que os processadores quânticos estejam disponíveis ao público em geral, as sub-rotinas Q# são executadas num simulador.</span><span class="sxs-lookup"><span data-stu-id="b0c45-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="b0c45-112">A Q# fornece um pequeno conjunto de tipos primitivos, juntamente com duas formas (matrizes e cadeias de identificação) para criar novos tipos estruturados.</span><span class="sxs-lookup"><span data-stu-id="b0c45-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="b0c45-113">Suporta um modelo processual básico para escrita de programas, com ciclos e instruções if/when.</span><span class="sxs-lookup"><span data-stu-id="b0c45-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="b0c45-114">As construções de nível superior em Q# são tipos, operações e funções definidos por utilizadores.</span><span class="sxs-lookup"><span data-stu-id="b0c45-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="b0c45-115">As secções a seguir detalham:</span><span class="sxs-lookup"><span data-stu-id="b0c45-115">The following sections detail:</span></span>
- [<span data-ttu-id="b0c45-116">O Modelo de Tipo</span><span class="sxs-lookup"><span data-stu-id="b0c45-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="b0c45-117">Expressões</span><span class="sxs-lookup"><span data-stu-id="b0c45-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="b0c45-118">Instruções</span><span class="sxs-lookup"><span data-stu-id="b0c45-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="b0c45-119">Estrutura de Ficheiros</span><span class="sxs-lookup"><span data-stu-id="b0c45-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="b0c45-120">Convenções</span><span class="sxs-lookup"><span data-stu-id="b0c45-120">Conventions</span></span>

<span data-ttu-id="b0c45-121">Estamos a trabalhar no sentido de garantir que os sinais de pontuação comuns são utilizados de forma consistente em todas as situações.</span><span class="sxs-lookup"><span data-stu-id="b0c45-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="b0c45-122">Esperamos que isso torne a Q# mais fácil de aprender e ler, porque estes sinais têm sempre o mesmo significado, e o mesmo conceito é sempre representado da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="b0c45-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="b0c45-123">Mais concretamente:</span><span class="sxs-lookup"><span data-stu-id="b0c45-123">Specifically:</span></span>

- <span data-ttu-id="b0c45-124">O ponto e vírgula, `;`, é utilizado para terminar uma instrução ou diretiva de uma linha.</span><span class="sxs-lookup"><span data-stu-id="b0c45-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="b0c45-125">Não é utilizado para outros fins.</span><span class="sxs-lookup"><span data-stu-id="b0c45-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="b0c45-126">A vírgula, `,`, é utilizada para separar os elementos de uma sequência.</span><span class="sxs-lookup"><span data-stu-id="b0c45-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="b0c45-127">É utilizada em cadeias de identificação de literais, literais de matrizes, listas de argumentos, definições de cadeias de identificação e listas de tipos.</span><span class="sxs-lookup"><span data-stu-id="b0c45-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="b0c45-128">**Ao contrário das versões anteriores, o `;` já não é suportado como um separador de literais de matrizes.**</span><span class="sxs-lookup"><span data-stu-id="b0c45-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="b0c45-129">Os dois pontos, `:`, são utilizados para introduzir uma anotação de tipo.</span><span class="sxs-lookup"><span data-stu-id="b0c45-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="b0c45-130">São sobretudo utilizados em assinaturas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b0c45-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="b0c45-131">Uma vez que os dois pontos introduzem sempre uma assinatura de tipo, o operador condicional ternário, introduzido na versão 0.3, utiliza uma barra vertical, `|`, para separar os valores verdadeiros e falsos; por conseguinte, Q# utiliza `cond ? tval | fval` em vez do separador de dois pontos, tal como em C.</span><span class="sxs-lookup"><span data-stu-id="b0c45-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
