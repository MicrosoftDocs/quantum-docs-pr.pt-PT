---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Aplicação Operação Inscreva-se
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: e0c546b768320ce43e7b44242d15838194e1089d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717023"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="3454a-102">Aplicação Operação Inscreva-se</span><span class="sxs-lookup"><span data-stu-id="3454a-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="3454a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3454a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3454a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3454a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3454a-105">Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.</span><span class="sxs-lookup"><span data-stu-id="3454a-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="3454a-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="3454a-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3454a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="3454a-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="3454a-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="3454a-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3454a-109">Operação a aplicar ao subrecípida.</span><span class="sxs-lookup"><span data-stu-id="3454a-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="3454a-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3454a-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3454a-111">Matriz de índices, indicando a que qubits será aplicada a operação.</span><span class="sxs-lookup"><span data-stu-id="3454a-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3454a-112">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3454a-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3454a-113">Registe-se no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="3454a-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3454a-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3454a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3454a-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3454a-115">See Also</span></span>

- [<span data-ttu-id="3454a-116">Microsoft.Quantum.Canon.ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="3454a-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)