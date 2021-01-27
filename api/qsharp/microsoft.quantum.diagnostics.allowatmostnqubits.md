---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Permitir a operação DoMSTNQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830897"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="7e440-102">Permitir a operação DoMSTNQubits</span><span class="sxs-lookup"><span data-stu-id="7e440-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="7e440-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7e440-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7e440-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e440-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e440-105">Entre uma chamada para esta operação e o seu adjacente, afirma que, no máximo, um determinado número de qubits adicionais são atribuídos com recurso a declarações.</span><span class="sxs-lookup"><span data-stu-id="7e440-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="7e440-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7e440-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="7e440-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e440-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e440-108">O número máximo de qubits que podem ser atribuídos.</span><span class="sxs-lookup"><span data-stu-id="7e440-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="7e440-109">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7e440-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7e440-110">Uma mensagem a ser exibida após o fracasso.</span><span class="sxs-lookup"><span data-stu-id="7e440-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e440-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e440-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="7e440-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7e440-112">Example</span></span>

<span data-ttu-id="7e440-113">O seguinte corte falhará quando executado em máquinas que suportam este diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="7e440-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="7e440-114">Observações</span><span class="sxs-lookup"><span data-stu-id="7e440-114">Remarks</span></span>

<span data-ttu-id="7e440-115">Esta operação pode ser substituída por um não-operatório sobre alvos que não a suportem.</span><span class="sxs-lookup"><span data-stu-id="7e440-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>