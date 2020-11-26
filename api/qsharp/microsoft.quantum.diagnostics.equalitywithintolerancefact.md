---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceSsa função
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201721"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="00fb2-102">EqualityWithinToleranceSsa função</span><span class="sxs-lookup"><span data-stu-id="00fb2-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="00fb2-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="00fb2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="00fb2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00fb2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00fb2-105">Representa a alegação de que um valor clássico do ponto flutuante tem o valor esperado até uma certa tolerância absoluta.</span><span class="sxs-lookup"><span data-stu-id="00fb2-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="00fb2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="00fb2-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="00fb2-107">real : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00fb2-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00fb2-108">O número a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="00fb2-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="00fb2-109">esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00fb2-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00fb2-110">O valor esperado.</span><span class="sxs-lookup"><span data-stu-id="00fb2-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="00fb2-111">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00fb2-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00fb2-112">Tolerância absoluta na diferença entre real e esperado.</span><span class="sxs-lookup"><span data-stu-id="00fb2-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00fb2-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00fb2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

