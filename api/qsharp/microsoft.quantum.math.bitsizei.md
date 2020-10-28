---
uid: Microsoft.Quantum.Math.BitSizeI
title: Função BitSizeI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723198"
---
# <a name="bitsizei-function"></a><span data-ttu-id="849e3-102">Função BitSizeI</span><span class="sxs-lookup"><span data-stu-id="849e3-102">BitSizeI function</span></span>

<span data-ttu-id="849e3-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="849e3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="849e3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="849e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="849e3-105">Para um número inteiro não `a` negativo, devolve o número de bits necessários para representar `a` .</span><span class="sxs-lookup"><span data-stu-id="849e3-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="849e3-106">Ou seja, devolve o menor $n$ de tal forma que $a < 2^n$.</span><span class="sxs-lookup"><span data-stu-id="849e3-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="849e3-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="849e3-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="849e3-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="849e3-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="849e3-109">O inteiro cujo tamanho bit deve ser calculado.</span><span class="sxs-lookup"><span data-stu-id="849e3-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="849e3-110">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="849e3-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="849e3-111">O tamanho `a` de.</span><span class="sxs-lookup"><span data-stu-id="849e3-111">The bit-size of `a`.</span></span>