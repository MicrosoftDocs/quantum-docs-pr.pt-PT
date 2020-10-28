---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Permitir a operação DoMSTNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713058"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="66c48-102">Permitir a operação DoMSTNQubits</span><span class="sxs-lookup"><span data-stu-id="66c48-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="66c48-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="66c48-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="66c48-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66c48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66c48-105">Entre uma chamada para esta operação e o seu adjacente, afirma que, no máximo, um determinado número de qubits adicionais são atribuídos com recurso a declarações.</span><span class="sxs-lookup"><span data-stu-id="66c48-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="66c48-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="66c48-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="66c48-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66c48-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66c48-108">O número máximo de qubits que podem ser atribuídos.</span><span class="sxs-lookup"><span data-stu-id="66c48-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="66c48-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="66c48-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="66c48-110">Uma mensagem a ser exibida após o fracasso.</span><span class="sxs-lookup"><span data-stu-id="66c48-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66c48-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66c48-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="66c48-112">Observações</span><span class="sxs-lookup"><span data-stu-id="66c48-112">Remarks</span></span>

<span data-ttu-id="66c48-113">Esta operação pode ser substituída por um não-operatório sobre alvos que não a suportem.</span><span class="sxs-lookup"><span data-stu-id="66c48-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>