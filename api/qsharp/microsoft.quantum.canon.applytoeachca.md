---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: Aplicação OperaçãoToachCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717552"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="bec20-102">Aplicação OperaçãoToachCA</span><span class="sxs-lookup"><span data-stu-id="bec20-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="bec20-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bec20-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bec20-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bec20-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bec20-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="bec20-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="bec20-106">O modificador `CA` indica que a operação de um único qubit é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="bec20-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bec20-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="bec20-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="bec20-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="bec20-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="bec20-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="bec20-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bec20-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="bec20-110">register : 'T[]</span></span>

<span data-ttu-id="bec20-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="bec20-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bec20-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bec20-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bec20-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bec20-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bec20-114">'T</span><span class="sxs-lookup"><span data-stu-id="bec20-114">'T</span></span>

<span data-ttu-id="bec20-115">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="bec20-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bec20-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bec20-116">See Also</span></span>

- [<span data-ttu-id="bec20-117">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="bec20-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)