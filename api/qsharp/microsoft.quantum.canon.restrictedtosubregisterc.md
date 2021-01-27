---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: Função restrita DoubregisterC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f44e9ea4d17dcadc6d3c64941529db819b7f9784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840210"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="8173f-102">Função restrita DoubregisterC</span><span class="sxs-lookup"><span data-stu-id="8173f-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="8173f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8173f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8173f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8173f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8173f-105">Restringe uma operação a um conjunto de índices de um registo, isto é, um subrecretário.</span><span class="sxs-lookup"><span data-stu-id="8173f-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="8173f-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="8173f-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="8173f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8173f-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="8173f-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="8173f-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8173f-109">Operação a restringir a um subregister.</span><span class="sxs-lookup"><span data-stu-id="8173f-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="8173f-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8173f-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8173f-111">Matriz de índices, indicando a que qubits a operação será restringida.</span><span class="sxs-lookup"><span data-stu-id="8173f-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-ctl"></a><span data-ttu-id="8173f-112">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="8173f-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="8173f-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8173f-113">See Also</span></span>

- [<span data-ttu-id="8173f-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="8173f-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)