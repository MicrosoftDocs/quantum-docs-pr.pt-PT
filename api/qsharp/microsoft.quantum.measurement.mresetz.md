---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operação MResetZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853747"
---
# <a name="mresetz-operation"></a><span data-ttu-id="41913-102">Operação MResetZ</span><span class="sxs-lookup"><span data-stu-id="41913-102">MResetZ operation</span></span>

<span data-ttu-id="41913-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="41913-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="41913-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="41913-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="41913-105">Mede um único qubit na base Z e repõe-o para um estado inicial fixo após a medição.</span><span class="sxs-lookup"><span data-stu-id="41913-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="41913-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="41913-106">Description</span></span>

<span data-ttu-id="41913-107">Executa uma medição de um único qubit na base de $Z$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.</span><span class="sxs-lookup"><span data-stu-id="41913-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="41913-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="41913-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="41913-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="41913-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="41913-110">Um único qubit a medir.</span><span class="sxs-lookup"><span data-stu-id="41913-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="41913-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="41913-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="41913-112">O resultado da medição `target` na base pauli $Z$.</span><span class="sxs-lookup"><span data-stu-id="41913-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>