---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: Função IsCoprimeI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723355"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="5de4a-102">Função IsCoprimeI</span><span class="sxs-lookup"><span data-stu-id="5de4a-102">IsCoprimeI function</span></span>

<span data-ttu-id="5de4a-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5de4a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5de4a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5de4a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5de4a-105">Devoluções verdadeiras se $a$ e $b$ são co-prime e falso de outra forma.</span><span class="sxs-lookup"><span data-stu-id="5de4a-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="5de4a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5de4a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5de4a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5de4a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5de4a-108">o primeiro número de que a co-primalidade está a ser testada</span><span class="sxs-lookup"><span data-stu-id="5de4a-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="5de4a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5de4a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5de4a-110">o segundo número de que co-primalidade está a ser testada</span><span class="sxs-lookup"><span data-stu-id="5de4a-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="5de4a-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5de4a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5de4a-112">É verdade, se $a$ e $b$ são co-prime (por exemplo, o seu maior divisor comum é 1), e falso de outra forma</span><span class="sxs-lookup"><span data-stu-id="5de4a-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>