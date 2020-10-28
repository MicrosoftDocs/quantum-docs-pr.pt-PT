---
uid: Microsoft.Quantum.Measurement.MultiM
title: Operação MultiM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711042"
---
# <a name="multim-operation"></a><span data-ttu-id="bdea1-102">Operação MultiM</span><span class="sxs-lookup"><span data-stu-id="bdea1-102">MultiM operation</span></span>

<span data-ttu-id="bdea1-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="bdea1-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="bdea1-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bdea1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bdea1-105">Mede cada qubit numa determinada matriz na base padrão.</span><span class="sxs-lookup"><span data-stu-id="bdea1-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="bdea1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bdea1-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="bdea1-107">alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bdea1-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bdea1-108">Uma série de qubits a medir.</span><span class="sxs-lookup"><span data-stu-id="bdea1-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="bdea1-109">Saída: __<Result> inválido__ []</span><span class="sxs-lookup"><span data-stu-id="bdea1-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="bdea1-110">Uma série de resultados de medição.</span><span class="sxs-lookup"><span data-stu-id="bdea1-110">An array of measurement results.</span></span>