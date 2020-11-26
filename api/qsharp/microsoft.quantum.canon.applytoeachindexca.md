---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: AplicaçãoToAchIndexCA operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208946"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="6130c-102">AplicaçãoToAchIndexCA operação</span><span class="sxs-lookup"><span data-stu-id="6130c-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="6130c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6130c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6130c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6130c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6130c-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="6130c-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="6130c-106">O modificador `CA` indica que a operação de um único qubit é adjacente e controlável.</span><span class="sxs-lookup"><span data-stu-id="6130c-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6130c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6130c-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="6130c-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="6130c-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6130c-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="6130c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6130c-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="6130c-110">register : 'T[]</span></span>

<span data-ttu-id="6130c-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="6130c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6130c-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6130c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6130c-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="6130c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6130c-114">'T</span><span class="sxs-lookup"><span data-stu-id="6130c-114">'T</span></span>

<span data-ttu-id="6130c-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="6130c-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6130c-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6130c-116">See Also</span></span>

- [<span data-ttu-id="6130c-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="6130c-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)