---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: Melhor Função DeDivisorL do MaiorCommon
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1bd18758bb2dea8a4801cbfdf258d91f81c5d9a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195515"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="d90ef-102">Melhor Função DeDivisorL do MaiorCommon</span><span class="sxs-lookup"><span data-stu-id="d90ef-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="d90ef-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d90ef-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d90ef-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d90ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d90ef-105">Calcula o maior divisor comum de $a$ e $b$.</span><span class="sxs-lookup"><span data-stu-id="d90ef-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="d90ef-106">O GCD é sempre positivo.</span><span class="sxs-lookup"><span data-stu-id="d90ef-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="d90ef-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d90ef-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d90ef-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d90ef-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d90ef-109">o primeiro número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="d90ef-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d90ef-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d90ef-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d90ef-111">o segundo número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="d90ef-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="d90ef-112">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d90ef-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d90ef-113">Maior divisor comum de $a$ e $b$</span><span class="sxs-lookup"><span data-stu-id="d90ef-113">Greatest common divisor of $a$ and $b$</span></span>