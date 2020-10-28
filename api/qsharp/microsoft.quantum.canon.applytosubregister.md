---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Aplicação Operação Deubregister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717034"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="47f45-102">Aplicação Operação Deubregister</span><span class="sxs-lookup"><span data-stu-id="47f45-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="47f45-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47f45-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47f45-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47f45-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47f45-105">Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.</span><span class="sxs-lookup"><span data-stu-id="47f45-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="47f45-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="47f45-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="47f45-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="47f45-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="47f45-108">Operação a aplicar ao subrecípida.</span><span class="sxs-lookup"><span data-stu-id="47f45-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="47f45-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="47f45-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="47f45-110">Matriz de índices, indicando a que qubits será aplicada a operação.</span><span class="sxs-lookup"><span data-stu-id="47f45-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="47f45-111">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="47f45-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="47f45-112">Registe-se no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="47f45-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47f45-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47f45-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="47f45-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="47f45-114">See Also</span></span>

- [<span data-ttu-id="47f45-115">Microsoft.Quantum.Canon.ApplyToSubregistera</span><span class="sxs-lookup"><span data-stu-id="47f45-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="47f45-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="47f45-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="47f45-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="47f45-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)