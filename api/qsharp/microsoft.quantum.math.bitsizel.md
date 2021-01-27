---
uid: Microsoft.Quantum.Math.BitSizeL
title: Função BitSizeL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848917"
---
# <a name="bitsizel-function"></a><span data-ttu-id="69c11-102">Função BitSizeL</span><span class="sxs-lookup"><span data-stu-id="69c11-102">BitSizeL function</span></span>

<span data-ttu-id="69c11-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="69c11-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="69c11-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69c11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69c11-105">Para um número inteiro não `a` negativo, devolve o número de bits necessários para representar `a` .</span><span class="sxs-lookup"><span data-stu-id="69c11-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="69c11-106">Ou seja, devolve o menor $n$ de tal forma que $a < 2^n$.</span><span class="sxs-lookup"><span data-stu-id="69c11-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="69c11-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="69c11-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="69c11-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69c11-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69c11-109">O inteiro cujo tamanho bit deve ser calculado.</span><span class="sxs-lookup"><span data-stu-id="69c11-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="69c11-110">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69c11-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69c11-111">O tamanho `a` de.</span><span class="sxs-lookup"><span data-stu-id="69c11-111">The bit-size of `a`.</span></span>