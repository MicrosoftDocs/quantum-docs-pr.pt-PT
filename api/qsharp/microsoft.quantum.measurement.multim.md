---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operação MultiM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857000"
---
# <a name="multim-operation"></a><span data-ttu-id="7e0f8-102">Operação MultiM</span><span class="sxs-lookup"><span data-stu-id="7e0f8-102">MultiM operation</span></span>

<span data-ttu-id="7e0f8-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="7e0f8-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="7e0f8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e0f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e0f8-105">Mede cada qubit numa determinada matriz na base padrão.</span><span class="sxs-lookup"><span data-stu-id="7e0f8-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="7e0f8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7e0f8-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="7e0f8-107">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7e0f8-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7e0f8-108">Uma série de qubits a medir.</span><span class="sxs-lookup"><span data-stu-id="7e0f8-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="7e0f8-109">Saída: __<Result> inválido__[]</span><span class="sxs-lookup"><span data-stu-id="7e0f8-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="7e0f8-110">Uma série de resultados de medição.</span><span class="sxs-lookup"><span data-stu-id="7e0f8-110">An array of measurement results.</span></span>