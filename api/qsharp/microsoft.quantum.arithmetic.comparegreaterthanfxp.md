---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: Comparar operação CompareGreaterThanFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223532"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="2e0b0-102">Comparar operação CompareGreaterThanFxP</span><span class="sxs-lookup"><span data-stu-id="2e0b0-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="2e0b0-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2e0b0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2e0b0-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="2e0b0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="2e0b0-105">Compara dois números de pontos fixos armazenados em registos quânticos e controla uma inversão do resultado.</span><span class="sxs-lookup"><span data-stu-id="2e0b0-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2e0b0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e0b0-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="2e0b0-107">FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="2e0b0-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="2e0b0-108">Primeiro número de ponto fixo a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="2e0b0-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="2e0b0-109">FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="2e0b0-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="2e0b0-110">Segundo número de ponto fixo a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="2e0b0-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="2e0b0-111">resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2e0b0-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2e0b0-112">Resultado da comparação.</span><span class="sxs-lookup"><span data-stu-id="2e0b0-112">Result of the comparison.</span></span> <span data-ttu-id="2e0b0-113">Será virado se `fp1 > fp2` . .</span><span class="sxs-lookup"><span data-stu-id="2e0b0-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e0b0-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e0b0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2e0b0-115">Observações</span><span class="sxs-lookup"><span data-stu-id="2e0b0-115">Remarks</span></span>

<span data-ttu-id="2e0b0-116">A atual implementação requer que os dois números de ponto fixo tenham a mesma posição e o mesmo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="2e0b0-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>