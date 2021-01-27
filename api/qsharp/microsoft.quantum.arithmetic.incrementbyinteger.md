---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operação IncrementByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 9c7ff6947964a4dbe07106d1def9be46f631f5cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843159"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="59e38-102">Operação IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="59e38-102">IncrementByInteger operation</span></span>

<span data-ttu-id="59e38-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="59e38-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="59e38-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59e38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59e38-105">Incrementa um registo quântico não assinado por um inteiro clássico, usando rotações de fase.</span><span class="sxs-lookup"><span data-stu-id="59e38-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="59e38-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="59e38-106">Description</span></span>

<span data-ttu-id="59e38-107">Suponha que `target` codifica um inteiro não assinado $x$ em uma codificação pouco endiana e isso é igual a `increment` $a$.</span><span class="sxs-lookup"><span data-stu-id="59e38-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="59e38-108">Em seguida, esta operação implementa o unitário $\ket{x} \mapsto \ket{x + a}$, onde a adição é realizada modulo $2^n$, onde $n = \texttt{Comprimento (alvo!)} $.</span><span class="sxs-lookup"><span data-stu-id="59e38-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="59e38-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="59e38-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="59e38-110">incremento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59e38-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59e38-111">O inteiro pelo qual o `target` é incrementado por.</span><span class="sxs-lookup"><span data-stu-id="59e38-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="59e38-112">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="59e38-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="59e38-113">Um registo quântico que codifica um número inteiro não assinado usando a codificação de pequenas extremidades.</span><span class="sxs-lookup"><span data-stu-id="59e38-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59e38-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59e38-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

