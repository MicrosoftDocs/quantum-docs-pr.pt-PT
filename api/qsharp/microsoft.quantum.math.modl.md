---
uid: Microsoft.Quantum.Math.ModL
title: Função ModL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723103"
---
# <a name="modl-function"></a><span data-ttu-id="c07f4-102">Função ModL</span><span class="sxs-lookup"><span data-stu-id="c07f4-102">ModL function</span></span>

<span data-ttu-id="c07f4-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c07f4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c07f4-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c07f4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c07f4-105">Devolve o módulo de um número em relação a outro número.</span><span class="sxs-lookup"><span data-stu-id="c07f4-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="c07f4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c07f4-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c07f4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c07f4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c07f4-108">A entrada $a$ cujo módulo deve ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="c07f4-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c07f4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c07f4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c07f4-110">O número em relação ao qual o módulo de $a$ deve ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="c07f4-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="c07f4-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c07f4-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c07f4-112">O módulo $a \bmod b$.</span><span class="sxs-lookup"><span data-stu-id="c07f4-112">The modulus $a \bmod b$.</span></span>