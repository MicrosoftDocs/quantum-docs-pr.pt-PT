---
uid: Microsoft.Quantum.Math.BitSizeL
title: Função BitSizeL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723187"
---
# <a name="bitsizel-function"></a><span data-ttu-id="4b510-102">Função BitSizeL</span><span class="sxs-lookup"><span data-stu-id="4b510-102">BitSizeL function</span></span>

<span data-ttu-id="4b510-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4b510-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4b510-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b510-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b510-105">Para um número inteiro não `a` negativo, devolve o número de bits necessários para representar `a` .</span><span class="sxs-lookup"><span data-stu-id="4b510-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="4b510-106">Ou seja, devolve o menor $n$ de tal forma que $a < 2^n$.</span><span class="sxs-lookup"><span data-stu-id="4b510-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="4b510-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="4b510-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4b510-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4b510-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4b510-109">O inteiro cujo tamanho bit deve ser calculado.</span><span class="sxs-lookup"><span data-stu-id="4b510-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="4b510-110">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b510-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b510-111">O tamanho `a` de.</span><span class="sxs-lookup"><span data-stu-id="4b510-111">The bit-size of `a`.</span></span>