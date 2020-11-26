---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Aplicação Operação Inscreva-se
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: edea0e565984cffb13b146cb336f90762f647636
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208062"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="7d08f-102">Aplicação Operação Inscreva-se</span><span class="sxs-lookup"><span data-stu-id="7d08f-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="7d08f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7d08f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7d08f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d08f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d08f-105">Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.</span><span class="sxs-lookup"><span data-stu-id="7d08f-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="7d08f-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="7d08f-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="7d08f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7d08f-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="7d08f-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="7d08f-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7d08f-109">Operação a aplicar ao subrecípida.</span><span class="sxs-lookup"><span data-stu-id="7d08f-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="7d08f-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7d08f-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7d08f-111">Matriz de índices, indicando a que qubits será aplicada a operação.</span><span class="sxs-lookup"><span data-stu-id="7d08f-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7d08f-112">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7d08f-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7d08f-113">Registe-se no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="7d08f-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d08f-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d08f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7d08f-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7d08f-115">See Also</span></span>

- [<span data-ttu-id="7d08f-116">Microsoft.Quantum.Canon.ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="7d08f-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)