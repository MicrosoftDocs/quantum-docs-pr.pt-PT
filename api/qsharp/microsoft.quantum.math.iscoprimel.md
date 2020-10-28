---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: Função IsCoprimeL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722305"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="b3271-102">Função IsCoprimeL</span><span class="sxs-lookup"><span data-stu-id="b3271-102">IsCoprimeL function</span></span>

<span data-ttu-id="b3271-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b3271-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b3271-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3271-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3271-105">Devoluções verdadeiras se $a$ e $b$ são co-prime e falso de outra forma.</span><span class="sxs-lookup"><span data-stu-id="b3271-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="b3271-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b3271-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b3271-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b3271-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b3271-108">o primeiro número de que a co-primalidade está a ser testada</span><span class="sxs-lookup"><span data-stu-id="b3271-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b3271-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b3271-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b3271-110">o segundo número de que co-primalidade está a ser testada</span><span class="sxs-lookup"><span data-stu-id="b3271-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="b3271-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b3271-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b3271-112">É verdade, se $a$ e $b$ são co-prime (por exemplo, o seu maior divisor comum é 1), e falso de outra forma</span><span class="sxs-lookup"><span data-stu-id="b3271-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>