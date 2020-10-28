---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: Operação MultiplyFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719782"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="e8076-102">Operação MultiplyFxP</span><span class="sxs-lookup"><span data-stu-id="e8076-102">MultiplyFxP operation</span></span>

<span data-ttu-id="e8076-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e8076-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e8076-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8076-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8076-105">Multiplica dois números de pontos fixos nos registos quânticos.</span><span class="sxs-lookup"><span data-stu-id="e8076-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="e8076-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e8076-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="e8076-107">FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e8076-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e8076-108">Primeiro número de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="e8076-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="e8076-109">FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e8076-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e8076-110">Segundo ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="e8076-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="e8076-111">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="e8076-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="e8076-112">Resultado ponto fixo, deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="e8076-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8076-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8076-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e8076-114">Observações</span><span class="sxs-lookup"><span data-stu-id="e8076-114">Remarks</span></span>

<span data-ttu-id="e8076-115">A atual implementação requer que os três números de pontos fixos tenham a mesma posição e o mesmo número de qubits.</span><span class="sxs-lookup"><span data-stu-id="e8076-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>