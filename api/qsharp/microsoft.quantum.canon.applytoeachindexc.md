---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Aplicação Operação SeachIndexC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717527"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="cf002-102">Aplicação Operação SeachIndexC</span><span class="sxs-lookup"><span data-stu-id="cf002-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="cf002-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cf002-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cf002-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf002-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf002-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="cf002-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="cf002-106">O modificador `C` indica que a operação de um único qubit é controlável.</span><span class="sxs-lookup"><span data-stu-id="cf002-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cf002-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cf002-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-ctl"></a><span data-ttu-id="cf002-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="cf002-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="cf002-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="cf002-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="cf002-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="cf002-110">register : 'T[]</span></span>

<span data-ttu-id="cf002-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="cf002-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf002-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf002-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cf002-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="cf002-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cf002-114">'T</span><span class="sxs-lookup"><span data-stu-id="cf002-114">'T</span></span>

<span data-ttu-id="cf002-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="cf002-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf002-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cf002-116">See Also</span></span>

- [<span data-ttu-id="cf002-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="cf002-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)