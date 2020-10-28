---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: Melhor Função DeDivisorL do MaiorCommon
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723646"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="cc0a6-102">Melhor Função DeDivisorL do MaiorCommon</span><span class="sxs-lookup"><span data-stu-id="cc0a6-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="cc0a6-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cc0a6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cc0a6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc0a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc0a6-105">Calcula o maior divisor comum de $a$ e $b$.</span><span class="sxs-lookup"><span data-stu-id="cc0a6-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="cc0a6-106">O GCD é sempre positivo.</span><span class="sxs-lookup"><span data-stu-id="cc0a6-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="cc0a6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cc0a6-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cc0a6-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc0a6-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc0a6-109">o primeiro número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="cc0a6-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cc0a6-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc0a6-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc0a6-111">o segundo número do qual o divisor mais alargado está a ser calculado</span><span class="sxs-lookup"><span data-stu-id="cc0a6-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="cc0a6-112">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cc0a6-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cc0a6-113">Maior divisor comum de $a$ e $b$</span><span class="sxs-lookup"><span data-stu-id="cc0a6-113">Greatest common divisor of $a$ and $b$</span></span>