---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: Função RestritaToSubregisterA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: c260a0e422d7ffb8137f6ac41e1cb398b2f4a2a7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852186"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="9eb84-102">Função RestritaToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="9eb84-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="9eb84-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9eb84-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9eb84-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9eb84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9eb84-105">Restringe uma operação a um conjunto de índices de um registo, isto é, um subrecretário.</span><span class="sxs-lookup"><span data-stu-id="9eb84-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="9eb84-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="9eb84-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="9eb84-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="9eb84-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="9eb84-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="9eb84-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9eb84-109">Operação a restringir a um subregister.</span><span class="sxs-lookup"><span data-stu-id="9eb84-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="9eb84-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9eb84-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9eb84-111">Matriz de índices, indicando a que qubits a operação será restringida.</span><span class="sxs-lookup"><span data-stu-id="9eb84-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-adj"></a><span data-ttu-id="9eb84-112">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="9eb84-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="9eb84-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9eb84-113">See Also</span></span>

- [<span data-ttu-id="9eb84-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="9eb84-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)