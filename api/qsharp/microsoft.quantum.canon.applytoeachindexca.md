---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: AplicaçãoToAchIndexCA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717513"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="ced22-102">AplicaçãoToAchIndexCA operação</span><span class="sxs-lookup"><span data-stu-id="ced22-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="ced22-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ced22-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ced22-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ced22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ced22-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="ced22-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="ced22-106">O modificador `CA` indica que a operação de um único qubit é adjacente e controlável.</span><span class="sxs-lookup"><span data-stu-id="ced22-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ced22-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ced22-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="ced22-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="ced22-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ced22-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="ced22-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="ced22-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="ced22-110">register : 'T[]</span></span>

<span data-ttu-id="ced22-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="ced22-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ced22-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ced22-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ced22-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ced22-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ced22-114">'T</span><span class="sxs-lookup"><span data-stu-id="ced22-114">'T</span></span>

<span data-ttu-id="ced22-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="ced22-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ced22-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ced22-116">See Also</span></span>

- [<span data-ttu-id="ced22-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="ced22-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)