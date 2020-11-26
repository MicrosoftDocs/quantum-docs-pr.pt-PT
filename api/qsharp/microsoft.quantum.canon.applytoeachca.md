---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Aplicação OperaçãoToachCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217752"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="cc3fc-102">Aplicação OperaçãoToachCA</span><span class="sxs-lookup"><span data-stu-id="cc3fc-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="cc3fc-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc3fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc3fc-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc3fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc3fc-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="cc3fc-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="cc3fc-106">O modificador `CA` indica que a operação de um único qubit é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="cc3fc-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cc3fc-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cc3fc-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="cc3fc-108">singleElementOperation : 'T = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="cc3fc-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="cc3fc-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="cc3fc-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="cc3fc-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="cc3fc-110">register : 'T[]</span></span>

<span data-ttu-id="cc3fc-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="cc3fc-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc3fc-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc3fc-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cc3fc-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="cc3fc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc3fc-114">'T</span><span class="sxs-lookup"><span data-stu-id="cc3fc-114">'T</span></span>

<span data-ttu-id="cc3fc-115">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="cc3fc-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc3fc-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cc3fc-116">See Also</span></span>

- [<span data-ttu-id="cc3fc-117">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="cc3fc-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)