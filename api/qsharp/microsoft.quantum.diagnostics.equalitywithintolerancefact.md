---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceSsa função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712750"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="e8729-102">EqualityWithinToleranceSsa função</span><span class="sxs-lookup"><span data-stu-id="e8729-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="e8729-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e8729-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e8729-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8729-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8729-105">Representa a alegação de que um valor clássico do ponto flutuante tem o valor esperado até uma certa tolerância absoluta.</span><span class="sxs-lookup"><span data-stu-id="e8729-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="e8729-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e8729-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="e8729-107">real : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8729-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8729-108">O número a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="e8729-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="e8729-109">esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8729-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8729-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="e8729-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="e8729-111">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8729-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e8729-112">Tolerância absoluta na diferença entre real e esperado.</span><span class="sxs-lookup"><span data-stu-id="e8729-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8729-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8729-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

