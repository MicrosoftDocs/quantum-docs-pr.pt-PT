---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Permitir a operação DoMSTNQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202554"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="40dbd-102">Permitir a operação DoMSTNQubits</span><span class="sxs-lookup"><span data-stu-id="40dbd-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="40dbd-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="40dbd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="40dbd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40dbd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40dbd-105">Entre uma chamada para esta operação e o seu adjacente, afirma que, no máximo, um determinado número de qubits adicionais são atribuídos com recurso a declarações.</span><span class="sxs-lookup"><span data-stu-id="40dbd-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="40dbd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="40dbd-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="40dbd-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="40dbd-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="40dbd-108">O número máximo de qubits que podem ser atribuídos.</span><span class="sxs-lookup"><span data-stu-id="40dbd-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="40dbd-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="40dbd-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="40dbd-110">Uma mensagem a ser exibida após o fracasso.</span><span class="sxs-lookup"><span data-stu-id="40dbd-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40dbd-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40dbd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="40dbd-112">Observações</span><span class="sxs-lookup"><span data-stu-id="40dbd-112">Remarks</span></span>

<span data-ttu-id="40dbd-113">Esta operação pode ser substituída por um não-operatório sobre alvos que não a suportem.</span><span class="sxs-lookup"><span data-stu-id="40dbd-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>