---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operação MResetX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725004"
---
# <a name="mresetx-operation"></a><span data-ttu-id="02fc1-102">Operação MResetX</span><span class="sxs-lookup"><span data-stu-id="02fc1-102">MResetX operation</span></span>

<span data-ttu-id="02fc1-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="02fc1-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="02fc1-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02fc1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02fc1-105">Mede um único qubit na base X e repõe-o para um estado inicial fixo após a medição.</span><span class="sxs-lookup"><span data-stu-id="02fc1-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="02fc1-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="02fc1-106">Description</span></span>

<span data-ttu-id="02fc1-107">Executa uma medição de um único qubit na base de $X$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.</span><span class="sxs-lookup"><span data-stu-id="02fc1-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="02fc1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="02fc1-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="02fc1-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="02fc1-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="02fc1-110">Um único qubit a medir.</span><span class="sxs-lookup"><span data-stu-id="02fc1-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="02fc1-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="02fc1-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="02fc1-112">O resultado da medição `target` na base pauli $X$.</span><span class="sxs-lookup"><span data-stu-id="02fc1-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>