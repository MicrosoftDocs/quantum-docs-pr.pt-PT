---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: AplicaçãoToAchIndexCA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850804"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="f1488-102">AplicaçãoToAchIndexCA operação</span><span class="sxs-lookup"><span data-stu-id="f1488-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="f1488-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f1488-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f1488-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f1488-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f1488-105">Aplica uma operação de um único qubit a cada elemento indexado num registo.</span><span class="sxs-lookup"><span data-stu-id="f1488-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="f1488-106">O modificador `CA` indica que a operação de um único qubit é adjacente e controlável.</span><span class="sxs-lookup"><span data-stu-id="f1488-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f1488-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f1488-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="f1488-108">singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="f1488-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f1488-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="f1488-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f1488-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="f1488-110">register : 'T[]</span></span>

<span data-ttu-id="f1488-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="f1488-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1488-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1488-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f1488-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f1488-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1488-114">'T</span><span class="sxs-lookup"><span data-stu-id="f1488-114">'T</span></span>

<span data-ttu-id="f1488-115">O alvo em que cada uma das operações atua.</span><span class="sxs-lookup"><span data-stu-id="f1488-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1488-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f1488-116">See Also</span></span>

- [<span data-ttu-id="f1488-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="f1488-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)