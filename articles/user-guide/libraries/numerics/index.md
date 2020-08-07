---
title: Introdução à Biblioteca Numérica Quântica | Microsoft Docs
description: Introdução à Biblioteca Numérica Quântica
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: dc6407d9775ad8a401036912abd0b70033796144
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868785"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="f0bc7-103">Introdução à Biblioteca Numérica Quântica</span><span class="sxs-lookup"><span data-stu-id="f0bc7-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="f0bc7-104">Muitos algoritmos quânticos dependem de [oráculos](xref:microsoft.quantum.concepts.oracles) que avaliam as funções matemáticas numa sobreposição de entradas.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="f0bc7-105">O componente principal do algoritmo de Shor, por exemplo, avalia $f(x) = a^x\operatorname{mod} N$ para um $a$ fixo, o número do fator $N$ e $x$ num número inteiro $2n$-qubit numa sobreposição uniforme em todas as cadeias $2n$-bit.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="f0bc7-106">Para executar o algoritmo de Shor num computador quântico real, esta função tem de ser escrita em termos das operações nativas do computador de destino.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="f0bc7-107">Através da representação binária de $x$ com $x_i$ a denotar o bit $i$-th a contar do bit menos significante, $f(x)$ pode ser escrito como $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="f0bc7-108">Por sua vez, isto pode ser escrito como um produto (mod N) de termos $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="f0bc7-109">Assim, a função $f(x)$ pode ser implementada com uma sequência de multiplicações $2n$ (modulares) pela condicional $a^{2^i}$ em $x_i$ diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="f0bc7-110">As constantes $a^{2^i}$ podem ser calculadas previamente e reduzidas para o módulo N antes de executar o algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="f0bc7-111">Esta sequência de multiplicações modulares controladas pode ser ainda mais simplificadas: aada multiplicação pode ser executada com uma sequência de adições modulares $n$ controladas e cada adição modular pode ser criada a partir de uma adição regular e de um comparador.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="f0bc7-112">Tendo em conta que são necessários vários passos para chegar a uma implementação real, seria extremamente útil ter essas funcionalidades disponíveis desde o início.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="f0bc7-113">É por isso que o Quantum Development Kit fornece suporte para uma vasta variedade de funcionalidades numéricas.</span><span class="sxs-lookup"><span data-stu-id="f0bc7-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="f0bc7-114">Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="f0bc7-114">Functionality</span></span>

<span data-ttu-id="f0bc7-115">Além da aritmética de números inteiros mencionada até agora, a biblioteca numérica fornece:</span><span class="sxs-lookup"><span data-stu-id="f0bc7-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

- <span data-ttu-id="f0bc7-116">A funcionalidade de números inteiros com e sem sinal (multiplicação, quadrado, divisão com resto, inversão,etc.) com um ou dois números inteiros quânticos como entrada</span><span class="sxs-lookup"><span data-stu-id="f0bc7-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
- <span data-ttu-id="f0bc7-117">A funcionalidade de vírgula fixa (adição/subtração, multiplicação, quadrado, 1/x, avaliação polinomial) com um ou dois números quânticos de vírgula fixa como entrada</span><span class="sxs-lookup"><span data-stu-id="f0bc7-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="f0bc7-118">Introdução</span><span class="sxs-lookup"><span data-stu-id="f0bc7-118">Getting started</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f0bc7-119">Saiba como utilizar a biblioteca numérica</span><span class="sxs-lookup"><span data-stu-id="f0bc7-119">Learn about using the numerics library</span></span>](xref:microsoft.quantum.numerics.usage)
