---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operação MResetX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194207"
---
# <a name="mresetx-operation"></a><span data-ttu-id="79c03-102">Operação MResetX</span><span class="sxs-lookup"><span data-stu-id="79c03-102">MResetX operation</span></span>

<span data-ttu-id="79c03-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="79c03-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="79c03-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="79c03-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="79c03-105">Mede um único qubit na base X e repõe-o para um estado inicial fixo após a medição.</span><span class="sxs-lookup"><span data-stu-id="79c03-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="79c03-106">Description</span><span class="sxs-lookup"><span data-stu-id="79c03-106">Description</span></span>

<span data-ttu-id="79c03-107">Executa uma medição de um único qubit na base de $X$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.</span><span class="sxs-lookup"><span data-stu-id="79c03-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="79c03-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="79c03-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="79c03-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="79c03-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="79c03-110">Um único qubit a medir.</span><span class="sxs-lookup"><span data-stu-id="79c03-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="79c03-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="79c03-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="79c03-112">O resultado da medição `target` na base pauli $X$.</span><span class="sxs-lookup"><span data-stu-id="79c03-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>