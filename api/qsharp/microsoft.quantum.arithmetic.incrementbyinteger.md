---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operação IncrementByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222971"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="ebab6-102">Operação IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="ebab6-102">IncrementByInteger operation</span></span>

<span data-ttu-id="ebab6-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ebab6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ebab6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebab6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebab6-105">Incrementa um registo quântico não assinado por um inteiro clássico, usando rotações de fase.</span><span class="sxs-lookup"><span data-stu-id="ebab6-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ebab6-106">Description</span><span class="sxs-lookup"><span data-stu-id="ebab6-106">Description</span></span>

<span data-ttu-id="ebab6-107">Suponha que `target` codifica um inteiro não assinado $x$ em uma codificação pouco endiana e isso é igual a `increment` $a$.</span><span class="sxs-lookup"><span data-stu-id="ebab6-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="ebab6-108">Em seguida, esta operação implementa o unitário $\ket{x} \mapsto \ket{x + a}$, onde a adição é realizada modulo $2^n$, onde $n = \texttt{Comprimento (alvo!)} $.</span><span class="sxs-lookup"><span data-stu-id="ebab6-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="ebab6-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="ebab6-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="ebab6-110">incremento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebab6-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebab6-111">O inteiro pelo qual o `target` é incrementado por.</span><span class="sxs-lookup"><span data-stu-id="ebab6-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="ebab6-112">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ebab6-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ebab6-113">Um registo quântico que codifica um número inteiro não assinado usando a codificação de pequenas extremidades.</span><span class="sxs-lookup"><span data-stu-id="ebab6-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebab6-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebab6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

