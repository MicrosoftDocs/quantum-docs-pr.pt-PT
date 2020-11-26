---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: Função restrita DoubregistaToSubregister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a49b15ac9c3ba9c1959bdead11549c1f37caabf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205376"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="960e7-102">Função restrita DoubregistaToSubregister</span><span class="sxs-lookup"><span data-stu-id="960e7-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="960e7-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="960e7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="960e7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="960e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="960e7-105">Restringe uma operação a um conjunto de índices de um registo, isto é, um subrecretário.</span><span class="sxs-lookup"><span data-stu-id="960e7-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="960e7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="960e7-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="960e7-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="960e7-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="960e7-108">Operação a restringir a um subregister.</span><span class="sxs-lookup"><span data-stu-id="960e7-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="960e7-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="960e7-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="960e7-110">Matriz de índices, indicando a que qubits a operação será restringida.</span><span class="sxs-lookup"><span data-stu-id="960e7-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="960e7-111">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="960e7-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="960e7-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="960e7-112">See Also</span></span>

- [<span data-ttu-id="960e7-113">Microsoft.Quantum.Canon.RestrictedToSubregistera</span><span class="sxs-lookup"><span data-stu-id="960e7-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="960e7-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="960e7-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="960e7-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="960e7-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)