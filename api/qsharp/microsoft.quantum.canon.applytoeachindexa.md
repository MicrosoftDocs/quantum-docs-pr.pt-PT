---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: AplicaçãoToeachIndexA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850835"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="6b766-102">AplicaçãoToeachIndexA operação</span><span class="sxs-lookup"><span data-stu-id="6b766-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="6b766-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b766-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b766-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b766-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b766-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="6b766-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="6b766-106">O modificador `A` indica que a operação de um único qubit é adjacente.</span><span class="sxs-lookup"><span data-stu-id="6b766-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6b766-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6b766-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="6b766-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="6b766-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6b766-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="6b766-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6b766-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="6b766-110">register : 'T[]</span></span>

<span data-ttu-id="6b766-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="6b766-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b766-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b766-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b766-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="6b766-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b766-114">'T</span><span class="sxs-lookup"><span data-stu-id="6b766-114">'T</span></span>

<span data-ttu-id="6b766-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="6b766-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b766-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6b766-116">See Also</span></span>

- [<span data-ttu-id="6b766-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="6b766-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)