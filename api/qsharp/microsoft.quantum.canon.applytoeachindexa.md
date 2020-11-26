---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: AplicaçãoToeachIndexA operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217599"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="d7d64-102">AplicaçãoToeachIndexA operação</span><span class="sxs-lookup"><span data-stu-id="d7d64-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="d7d64-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7d64-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7d64-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7d64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7d64-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="d7d64-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="d7d64-106">O modificador `A` indica que a operação de um único qubit é adjacente.</span><span class="sxs-lookup"><span data-stu-id="d7d64-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d7d64-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d7d64-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="d7d64-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="d7d64-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d7d64-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="d7d64-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="d7d64-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d7d64-110">register : 'T[]</span></span>

<span data-ttu-id="d7d64-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="d7d64-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7d64-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7d64-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d7d64-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d7d64-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7d64-114">'T</span><span class="sxs-lookup"><span data-stu-id="d7d64-114">'T</span></span>

<span data-ttu-id="d7d64-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="d7d64-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7d64-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d7d64-116">See Also</span></span>

- [<span data-ttu-id="d7d64-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="d7d64-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)