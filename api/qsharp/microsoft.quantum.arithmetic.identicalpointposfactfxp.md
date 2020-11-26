---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: Função IdênticoPointPosFactFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223056"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="ef4bb-102">Função IdênticoPointPosFactFxP</span><span class="sxs-lookup"><span data-stu-id="ef4bb-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="ef4bb-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ef4bb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ef4bb-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="ef4bb-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="ef4bb-105">Afirma que todos os números de pontos fixos na matriz fornecida têm posições de ponto idênticas quando contam a partir da parte menos significativa.</span><span class="sxs-lookup"><span data-stu-id="ef4bb-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="ef4bb-106">Ou seja, o número de bits menos posição de ponto deve ser constante para todos os números de ponto fixo na matriz.</span><span class="sxs-lookup"><span data-stu-id="ef4bb-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ef4bb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ef4bb-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="ef4bb-108">pontos fixos : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="ef4bb-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="ef4bb-109">Matriz de números de pontos fixos quânticos que serão verificados para compatibilidade (usando afirmações).</span><span class="sxs-lookup"><span data-stu-id="ef4bb-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef4bb-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef4bb-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

