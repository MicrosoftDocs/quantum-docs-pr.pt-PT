---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: Aplicação Operação Inscreva-se
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 52564e64d8cc9cdbeb2626ed8694168b8ed48c22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850452"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="05d7d-102">Aplicação Operação Inscreva-se</span><span class="sxs-lookup"><span data-stu-id="05d7d-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="05d7d-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05d7d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05d7d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05d7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05d7d-105">Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.</span><span class="sxs-lookup"><span data-stu-id="05d7d-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="05d7d-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="05d7d-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="05d7d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="05d7d-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="05d7d-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="05d7d-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="05d7d-109">Operação a aplicar ao subrecípida.</span><span class="sxs-lookup"><span data-stu-id="05d7d-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="05d7d-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="05d7d-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="05d7d-111">Matriz de índices, indicando a que qubits será aplicada a operação.</span><span class="sxs-lookup"><span data-stu-id="05d7d-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="05d7d-112">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="05d7d-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="05d7d-113">Registe-se no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="05d7d-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05d7d-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05d7d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="05d7d-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="05d7d-115">See Also</span></span>

- [<span data-ttu-id="05d7d-116">Microsoft.Quantum.Canon.ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="05d7d-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)