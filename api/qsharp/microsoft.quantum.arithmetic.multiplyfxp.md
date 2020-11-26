---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operação MultiplyFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222614"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="82962-102">Operação MultiplyFxP</span><span class="sxs-lookup"><span data-stu-id="82962-102">MultiplyFxP operation</span></span>

<span data-ttu-id="82962-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="82962-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="82962-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="82962-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="82962-105">Multiplica dois números de pontos fixos nos registos quânticos.</span><span class="sxs-lookup"><span data-stu-id="82962-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="82962-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="82962-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="82962-107">FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="82962-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="82962-108">Primeiro número de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="82962-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="82962-109">FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="82962-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="82962-110">Segundo ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="82962-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="82962-111">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="82962-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="82962-112">Resultado ponto fixo, deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="82962-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82962-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82962-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="82962-114">Observações</span><span class="sxs-lookup"><span data-stu-id="82962-114">Remarks</span></span>

<span data-ttu-id="82962-115">A atual implementação requer que os três números de pontos fixos tenham a mesma posição e o mesmo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="82962-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>