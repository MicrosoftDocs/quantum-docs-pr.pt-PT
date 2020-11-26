---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: Operação ComputeReciprocalFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223396"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="b555e-102">Operação ComputeReciprocalFxP</span><span class="sxs-lookup"><span data-stu-id="b555e-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="b555e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b555e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b555e-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b555e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b555e-105">Calcula $1/x$ para um número de ponto fixo $x$.</span><span class="sxs-lookup"><span data-stu-id="b555e-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b555e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b555e-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="b555e-107">x : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b555e-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b555e-108">Número de ponto fixo a ser invertido.</span><span class="sxs-lookup"><span data-stu-id="b555e-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="b555e-109">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b555e-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b555e-110">Número de ponto fixo que irá manter o resultado.</span><span class="sxs-lookup"><span data-stu-id="b555e-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="b555e-111">Deve ser inicializado para $\ket{0.0}$.</span><span class="sxs-lookup"><span data-stu-id="b555e-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b555e-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b555e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

