---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Comparar operação CompareGreaterThanFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721295"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="33aff-102">Comparar operação CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="33aff-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="33aff-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="33aff-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="33aff-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33aff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33aff-105">Compara dois números de pontos fixos armazenados em registos quânticos e controla uma inversão do resultado.</span><span class="sxs-lookup"><span data-stu-id="33aff-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="33aff-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="33aff-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="33aff-107">FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="33aff-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="33aff-108">Primeiro número de ponto fixo a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="33aff-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="33aff-109">FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="33aff-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="33aff-110">Segundo número de ponto fixo a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="33aff-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="33aff-111">resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="33aff-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="33aff-112">Resultado da comparação.</span><span class="sxs-lookup"><span data-stu-id="33aff-112">Result of the comparison.</span></span> <span data-ttu-id="33aff-113">Será virado se `fp1 > fp2` . .</span><span class="sxs-lookup"><span data-stu-id="33aff-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33aff-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33aff-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="33aff-115">Observações</span><span class="sxs-lookup"><span data-stu-id="33aff-115">Remarks</span></span>

<span data-ttu-id="33aff-116">A atual implementação requer que os dois números de ponto fixo tenham a mesma posição e o mesmo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="33aff-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>