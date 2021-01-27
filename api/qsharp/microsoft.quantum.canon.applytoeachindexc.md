---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Aplicação Operação SeachIndexC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850815"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="bc102-102">Aplicação Operação SeachIndexC</span><span class="sxs-lookup"><span data-stu-id="bc102-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="bc102-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc102-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc102-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc102-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc102-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="bc102-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="bc102-106">O modificador `C` indica que a operação de um único qubit é controlável.</span><span class="sxs-lookup"><span data-stu-id="bc102-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="bc102-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="bc102-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="bc102-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="bc102-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bc102-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="bc102-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bc102-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="bc102-110">register : 'T[]</span></span>

<span data-ttu-id="bc102-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="bc102-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc102-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc102-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc102-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bc102-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc102-114">'T</span><span class="sxs-lookup"><span data-stu-id="bc102-114">'T</span></span>

<span data-ttu-id="bc102-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="bc102-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc102-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bc102-116">See Also</span></span>

- [<span data-ttu-id="bc102-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="bc102-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)