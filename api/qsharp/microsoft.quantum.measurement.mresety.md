---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operação MResety
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725007"
---
# <a name="mresety-operation"></a><span data-ttu-id="d0ed3-102">Operação MResety</span><span class="sxs-lookup"><span data-stu-id="d0ed3-102">MResetY operation</span></span>

<span data-ttu-id="d0ed3-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="d0ed3-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="d0ed3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0ed3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0ed3-105">Mede um único qubit na base Y e repõe-o a um estado inicial fixo após a medição.</span><span class="sxs-lookup"><span data-stu-id="d0ed3-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="d0ed3-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d0ed3-106">Description</span></span>

<span data-ttu-id="d0ed3-107">Executa uma medição de um único qubit na base de $Y$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.</span><span class="sxs-lookup"><span data-stu-id="d0ed3-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="d0ed3-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d0ed3-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="d0ed3-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d0ed3-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d0ed3-110">Um único qubit a medir.</span><span class="sxs-lookup"><span data-stu-id="d0ed3-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="d0ed3-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="d0ed3-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="d0ed3-112">O resultado da medição `target` na base pauli $Y$.</span><span class="sxs-lookup"><span data-stu-id="d0ed3-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>