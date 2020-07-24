---
title: Introdução à Biblioteca Numérica Quântica | Microsoft Docs
description: Introdução à Biblioteca Numérica Quântica
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: 9552f3683e1df8cb10d19d0b3f85223df056f83d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871353"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Introdução à Biblioteca Numérica Quântica

Muitos algoritmos quânticos dependem de [oráculos](xref:microsoft.quantum.concepts.oracles) que avaliam as funções matemáticas numa sobreposição de entradas.
O componente principal do algoritmo de Shor, por exemplo, avalia $f(x) = a^x\operatorname{mod} N$ para um $a$ fixo, o número do fator $N$ e $x$ num número inteiro $2n$-qubit numa sobreposição uniforme em todas as cadeias $2n$-bit.

Para executar o algoritmo de Shor num computador quântico real, esta função tem de ser escrita em termos das operações nativas do computador de destino.
Através da representação binária de $x$ com $x_i$ a denotar o bit $i$-th a contar do bit menos significante, $f(x)$ pode ser escrito como $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.
Por sua vez, isto pode ser escrito como um produto (mod N) de termos $a^{2^i x_i}=(a^{2^i})^{x_i}$. Assim, a função $f(x)$ pode ser implementada com uma sequência de multiplicações $2n$ (modulares) pela condicional $a^{2^i}$ em $x_i$ diferente de zero. As constantes $a^{2^i}$ podem ser calculadas previamente e reduzidas para o módulo N antes de executar o algoritmo.

Esta sequência de multiplicações modulares controladas pode ser ainda mais simplificadas: aada multiplicação pode ser executada com uma sequência de adições modulares $n$ controladas e cada adição modular pode ser criada a partir de uma adição regular e de um comparador.


Tendo em conta que são necessários vários passos para chegar a uma implementação real, seria extremamente útil ter essas funcionalidades disponíveis desde o início.
É por isso que o Quantum Development Kit fornece suporte para uma vasta variedade de funcionalidades numéricas.


## <a name="functionality"></a>Funcionalidade

Além da aritmética de números inteiros mencionada até agora, a biblioteca numérica fornece:

- A funcionalidade de números inteiros com e sem sinal (multiplicação, quadrado, divisão com resto, inversão,etc.) com um ou dois números inteiros quânticos como entrada
- A funcionalidade de vírgula fixa (adição/subtração, multiplicação, quadrado, 1/x, avaliação polinomial) com um ou dois números quânticos de vírgula fixa como entrada

## <a name="getting-started"></a>Introdução

> [!div class="nextstepaction"]
> [Saiba como utilizar a biblioteca numérica](xref:microsoft.quantum.numerics.usage)
