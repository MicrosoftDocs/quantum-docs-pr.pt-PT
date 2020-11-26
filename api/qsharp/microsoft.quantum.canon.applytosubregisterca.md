---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Aplicação Operação Inscreva-seSubregisterCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: a5ebfb17b1e66bd509f3a562f852986c83d0fef0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208011"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="791b8-102">Aplicação Operação Inscreva-seSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="791b8-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="791b8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="791b8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="791b8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="791b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="791b8-105">Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.</span><span class="sxs-lookup"><span data-stu-id="791b8-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="791b8-106">O modificador `CA` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="791b8-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="791b8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="791b8-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="791b8-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="791b8-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="791b8-109">Operação a aplicar ao subrecípida.</span><span class="sxs-lookup"><span data-stu-id="791b8-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="791b8-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="791b8-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="791b8-111">Matriz de índices, indicando a que qubits será aplicada a operação.</span><span class="sxs-lookup"><span data-stu-id="791b8-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="791b8-112">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="791b8-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="791b8-113">Registe-se no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="791b8-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="791b8-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="791b8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="791b8-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="791b8-115">See Also</span></span>

- [<span data-ttu-id="791b8-116">Microsoft.Quantum.Canon.ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="791b8-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)