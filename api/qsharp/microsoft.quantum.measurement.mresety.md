---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operação MResety
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227034"
---
# <a name="mresety-operation"></a><span data-ttu-id="fff13-102">Operação MResety</span><span class="sxs-lookup"><span data-stu-id="fff13-102">MResetY operation</span></span>

<span data-ttu-id="fff13-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="fff13-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="fff13-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fff13-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fff13-105">Mede um único qubit na base Y e repõe-o a um estado inicial fixo após a medição.</span><span class="sxs-lookup"><span data-stu-id="fff13-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="fff13-106">Description</span><span class="sxs-lookup"><span data-stu-id="fff13-106">Description</span></span>

<span data-ttu-id="fff13-107">Executa uma medição de um único qubit na base de $Y$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.</span><span class="sxs-lookup"><span data-stu-id="fff13-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="fff13-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fff13-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="fff13-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fff13-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fff13-110">Um único qubit a medir.</span><span class="sxs-lookup"><span data-stu-id="fff13-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="fff13-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="fff13-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="fff13-112">O resultado da medição `target` na base pauli $Y$.</span><span class="sxs-lookup"><span data-stu-id="fff13-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>