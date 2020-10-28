---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: AplicaçãoToeachIndexA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717538"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="7c954-102">AplicaçãoToeachIndexA operação</span><span class="sxs-lookup"><span data-stu-id="7c954-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="7c954-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c954-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c954-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c954-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c954-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="7c954-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="7c954-106">O modificador `A` indica que a operação de um único qubit é adjacente.</span><span class="sxs-lookup"><span data-stu-id="7c954-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7c954-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7c954-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="7c954-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="7c954-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c954-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="7c954-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="7c954-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="7c954-110">register : 'T[]</span></span>

<span data-ttu-id="7c954-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="7c954-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c954-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c954-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7c954-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7c954-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c954-114">'T</span><span class="sxs-lookup"><span data-stu-id="7c954-114">'T</span></span>

<span data-ttu-id="7c954-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="7c954-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c954-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7c954-116">See Also</span></span>

- [<span data-ttu-id="7c954-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="7c954-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)