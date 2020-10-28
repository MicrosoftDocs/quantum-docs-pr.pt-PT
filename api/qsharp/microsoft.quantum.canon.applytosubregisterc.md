---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Aplicação Operação Inscreva-se
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: ba5be1e7e822197eb76aac029be8617a70d51ddb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717006"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="63d20-102">Aplicação Operação Inscreva-se</span><span class="sxs-lookup"><span data-stu-id="63d20-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="63d20-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63d20-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63d20-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63d20-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63d20-105">Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.</span><span class="sxs-lookup"><span data-stu-id="63d20-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="63d20-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="63d20-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="63d20-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="63d20-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="63d20-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="63d20-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="63d20-109">Operação a aplicar ao subrecípida.</span><span class="sxs-lookup"><span data-stu-id="63d20-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="63d20-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="63d20-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="63d20-111">Matriz de índices, indicando a que qubits será aplicada a operação.</span><span class="sxs-lookup"><span data-stu-id="63d20-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="63d20-112">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="63d20-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="63d20-113">Registe-se no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="63d20-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63d20-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63d20-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="63d20-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="63d20-115">See Also</span></span>

- [<span data-ttu-id="63d20-116">Microsoft.Quantum.Canon.ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="63d20-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)