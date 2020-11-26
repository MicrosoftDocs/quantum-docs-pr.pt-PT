---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Comparar operação CompareGTI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223481"
---
# <a name="comparegti-operation"></a><span data-ttu-id="659c1-102">Comparar operação CompareGTI</span><span class="sxs-lookup"><span data-stu-id="659c1-102">CompareGTI operation</span></span>

<span data-ttu-id="659c1-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="659c1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="659c1-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="659c1-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="659c1-105">Invólucro para comparação de inteiros: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="659c1-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="659c1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="659c1-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="659c1-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="659c1-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="659c1-108">Primeiro número de $n$-bit</span><span class="sxs-lookup"><span data-stu-id="659c1-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="659c1-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="659c1-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="659c1-110">Segundo número de $n$-bit</span><span class="sxs-lookup"><span data-stu-id="659c1-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="659c1-111">resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="659c1-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="659c1-112">Será virado se $x > y$</span><span class="sxs-lookup"><span data-stu-id="659c1-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="659c1-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="659c1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

