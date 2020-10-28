---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: Função IdênticoPointPosFactFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721115"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="1cd56-102">Função IdênticoPointPosFactFxP</span><span class="sxs-lookup"><span data-stu-id="1cd56-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="1cd56-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1cd56-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1cd56-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1cd56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1cd56-105">Afirma que todos os números de pontos fixos na matriz fornecida têm posições de ponto idênticas quando contam a partir da parte menos significativa.</span><span class="sxs-lookup"><span data-stu-id="1cd56-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="1cd56-106">Ou seja, o número de bits menos posição de ponto deve ser constante para todos os números de ponto fixo na matriz.</span><span class="sxs-lookup"><span data-stu-id="1cd56-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1cd56-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1cd56-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="1cd56-108">pontos fixos : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="1cd56-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="1cd56-109">Matriz de números de pontos fixos quânticos que serão verificados para compatibilidade (usando afirmações).</span><span class="sxs-lookup"><span data-stu-id="1cd56-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="1cd56-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1cd56-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

