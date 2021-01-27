---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Aplicação OperaçãoToachC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850841"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="8f97c-102">Aplicação OperaçãoToachC</span><span class="sxs-lookup"><span data-stu-id="8f97c-102">ApplyToEachC operation</span></span>

<span data-ttu-id="8f97c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f97c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f97c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f97c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f97c-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="8f97c-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="8f97c-106">O modificador `C` indica que a operação de um único qubit é controlável.</span><span class="sxs-lookup"><span data-stu-id="8f97c-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="8f97c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8f97c-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="8f97c-108">singleElementOperação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Ctl</span><span class="sxs-lookup"><span data-stu-id="8f97c-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8f97c-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="8f97c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="8f97c-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="8f97c-110">register : 'T[]</span></span>

<span data-ttu-id="8f97c-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="8f97c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f97c-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f97c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f97c-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8f97c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f97c-114">'T</span><span class="sxs-lookup"><span data-stu-id="8f97c-114">'T</span></span>

<span data-ttu-id="8f97c-115">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="8f97c-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="8f97c-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8f97c-116">Example</span></span>

<span data-ttu-id="8f97c-117">Prepare um estado de três qubits $\ket{+}$ estado:</span><span class="sxs-lookup"><span data-stu-id="8f97c-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="8f97c-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8f97c-118">See Also</span></span>

- [<span data-ttu-id="8f97c-119">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="8f97c-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)