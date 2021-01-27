---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Aplicação Operação Deubregister
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850476"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="f2403-102">Aplicação Operação Deubregister</span><span class="sxs-lookup"><span data-stu-id="f2403-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="f2403-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2403-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2403-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2403-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2403-105">Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.</span><span class="sxs-lookup"><span data-stu-id="f2403-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f2403-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f2403-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="f2403-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f2403-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f2403-108">Operação a aplicar ao subrecípida.</span><span class="sxs-lookup"><span data-stu-id="f2403-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="f2403-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f2403-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f2403-110">Matriz de índices, indicando a que qubits será aplicada a operação.</span><span class="sxs-lookup"><span data-stu-id="f2403-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f2403-111">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2403-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2403-112">Registe-se no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="f2403-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2403-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2403-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="f2403-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f2403-114">Example</span></span>

<span data-ttu-id="f2403-115">Criar três qubit state $\frac {1} {\sqrt {2} }\ket {0} \_ 2(\ket {0} \_ 1\ket {0} _3+\ket {1} \_ 1\ket {1} _3)$:</span><span class="sxs-lookup"><span data-stu-id="f2403-115">Create three qubit state $\frac{1}{\sqrt{2}}\ket{0}\_2(\ket{0}\_1\ket{0}_3+\ket{1}\_1\ket{1}_3)$:</span></span>

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a><span data-ttu-id="f2403-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f2403-116">See Also</span></span>

- [<span data-ttu-id="f2403-117">Microsoft.Quantum.Canon.ApplyToSubregistera</span><span class="sxs-lookup"><span data-stu-id="f2403-117">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="f2403-118">Microsoft.Quantum.Canon.ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="f2403-118">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="f2403-119">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="f2403-119">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)