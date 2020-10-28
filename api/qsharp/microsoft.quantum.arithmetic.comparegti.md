---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Comparar operação CompareGTI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: c60c2827060f4ef223ebaf80ccdef09faaf56098
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721283"
---
# <a name="comparegti-operation"></a><span data-ttu-id="5d2db-102">Comparar operação CompareGTI</span><span class="sxs-lookup"><span data-stu-id="5d2db-102">CompareGTI operation</span></span>

<span data-ttu-id="5d2db-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5d2db-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5d2db-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d2db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d2db-105">Invólucro para comparação de inteiros: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="5d2db-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5d2db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5d2db-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="5d2db-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5d2db-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5d2db-108">Primeiro número de $n$-bit</span><span class="sxs-lookup"><span data-stu-id="5d2db-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="5d2db-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5d2db-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5d2db-110">Segundo número de $n$-bit</span><span class="sxs-lookup"><span data-stu-id="5d2db-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="5d2db-111">resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5d2db-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5d2db-112">Será virado se $x > y$</span><span class="sxs-lookup"><span data-stu-id="5d2db-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d2db-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d2db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

