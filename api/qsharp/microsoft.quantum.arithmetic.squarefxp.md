---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: Operação SquareFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: ba0364d7c649c2a949fc52f89409a5280f71a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842905"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="b1ea4-102">Operação SquareFxP</span><span class="sxs-lookup"><span data-stu-id="b1ea4-102">SquareFxP operation</span></span>

<span data-ttu-id="b1ea4-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b1ea4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b1ea4-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b1ea4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b1ea4-105">Quadrados um número de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="b1ea4-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b1ea4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b1ea4-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="b1ea4-107">FP : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b1ea4-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b1ea4-108">Número de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="b1ea4-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="b1ea4-109">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b1ea4-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b1ea4-110">Resultado ponto fixo, deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b1ea4-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1ea4-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1ea4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

