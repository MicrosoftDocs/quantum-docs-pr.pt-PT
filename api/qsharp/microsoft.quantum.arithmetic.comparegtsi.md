---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223498"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="14a04-102">CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="14a04-102">CompareGTSI operation</span></span>

<span data-ttu-id="14a04-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="14a04-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="14a04-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="14a04-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="14a04-105">Invólucro para comparação de inteiros assinado: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="14a04-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="14a04-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="14a04-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="14a04-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="14a04-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="14a04-108">Primeiro número de $n$-bit</span><span class="sxs-lookup"><span data-stu-id="14a04-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="14a04-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="14a04-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="14a04-110">Segundo número de $n$-bit</span><span class="sxs-lookup"><span data-stu-id="14a04-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="14a04-111">resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="14a04-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="14a04-112">Será virado se $xs > ys$</span><span class="sxs-lookup"><span data-stu-id="14a04-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="14a04-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14a04-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

