---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: AplicaçãoToEachIndex operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844597"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="71f9a-102">AplicaçãoToEachIndex operação</span><span class="sxs-lookup"><span data-stu-id="71f9a-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="71f9a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71f9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71f9a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71f9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71f9a-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="71f9a-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="71f9a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="71f9a-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="71f9a-107">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="71f9a-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="71f9a-108">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="71f9a-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="71f9a-109">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="71f9a-109">register : 'T[]</span></span>

<span data-ttu-id="71f9a-110">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="71f9a-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71f9a-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71f9a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71f9a-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="71f9a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71f9a-113">'T</span><span class="sxs-lookup"><span data-stu-id="71f9a-113">'T</span></span>

<span data-ttu-id="71f9a-114">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="71f9a-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="71f9a-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="71f9a-115">See Also</span></span>

- [<span data-ttu-id="71f9a-116">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="71f9a-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="71f9a-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="71f9a-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="71f9a-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="71f9a-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="71f9a-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="71f9a-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)