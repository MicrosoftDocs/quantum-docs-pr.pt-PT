---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Aplicação OperaçãoToachC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217786"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="d08cd-102">Aplicação OperaçãoToachC</span><span class="sxs-lookup"><span data-stu-id="d08cd-102">ApplyToEachC operation</span></span>

<span data-ttu-id="d08cd-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d08cd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d08cd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d08cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d08cd-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="d08cd-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="d08cd-106">O modificador `C` indica que a operação de um único qubit é controlável.</span><span class="sxs-lookup"><span data-stu-id="d08cd-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d08cd-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d08cd-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="d08cd-108">singleElementOperação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Ctl</span><span class="sxs-lookup"><span data-stu-id="d08cd-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d08cd-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="d08cd-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="d08cd-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d08cd-110">register : 'T[]</span></span>

<span data-ttu-id="d08cd-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="d08cd-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d08cd-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d08cd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d08cd-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d08cd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d08cd-114">'T</span><span class="sxs-lookup"><span data-stu-id="d08cd-114">'T</span></span>

<span data-ttu-id="d08cd-115">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="d08cd-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d08cd-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d08cd-116">See Also</span></span>

- [<span data-ttu-id="d08cd-117">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="d08cd-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)