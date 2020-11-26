---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operação MultiM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227000"
---
# <a name="multim-operation"></a><span data-ttu-id="129b9-102">Operação MultiM</span><span class="sxs-lookup"><span data-stu-id="129b9-102">MultiM operation</span></span>

<span data-ttu-id="129b9-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="129b9-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="129b9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="129b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="129b9-105">Mede cada qubit numa determinada matriz na base padrão.</span><span class="sxs-lookup"><span data-stu-id="129b9-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="129b9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="129b9-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="129b9-107">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="129b9-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="129b9-108">Uma série de qubits a medir.</span><span class="sxs-lookup"><span data-stu-id="129b9-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="129b9-109">Saída: __<Result> inválido__[]</span><span class="sxs-lookup"><span data-stu-id="129b9-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="129b9-110">Uma série de resultados de medição.</span><span class="sxs-lookup"><span data-stu-id="129b9-110">An array of measurement results.</span></span>