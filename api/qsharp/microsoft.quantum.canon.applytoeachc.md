---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Aplicação OperaçãoToachC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717566"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="93f28-102">Aplicação OperaçãoToachC</span><span class="sxs-lookup"><span data-stu-id="93f28-102">ApplyToEachC operation</span></span>

<span data-ttu-id="93f28-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93f28-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93f28-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93f28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93f28-105">Aplica uma operação de um único qubit a cada elemento num registo.</span><span class="sxs-lookup"><span data-stu-id="93f28-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="93f28-106">O modificador `C` indica que a operação de um único qubit é controlável.</span><span class="sxs-lookup"><span data-stu-id="93f28-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="93f28-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="93f28-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="93f28-108">única Cooperação de Estado: 'T = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93f28-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="93f28-109">Operação a aplicar a cada qubit.</span><span class="sxs-lookup"><span data-stu-id="93f28-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="93f28-110">registo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="93f28-110">register : 'T[]</span></span>

<span data-ttu-id="93f28-111">Matriz de qubits para aplicar a operação dada.</span><span class="sxs-lookup"><span data-stu-id="93f28-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93f28-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93f28-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="93f28-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="93f28-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93f28-114">'T</span><span class="sxs-lookup"><span data-stu-id="93f28-114">'T</span></span>

<span data-ttu-id="93f28-115">O alvo no qual a operação atua.</span><span class="sxs-lookup"><span data-stu-id="93f28-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="93f28-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="93f28-116">See Also</span></span>

- [<span data-ttu-id="93f28-117">Microsoft.Quantum.Canon.ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="93f28-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)