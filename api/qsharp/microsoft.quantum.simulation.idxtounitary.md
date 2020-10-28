---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: Função IdxToUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: a142d8a5af56a43de6341e3c0bdc77f50030f06e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710597"
---
# <a name="idxtounitary-function"></a><span data-ttu-id="e0c32-102">Função IdxToUnitary</span><span class="sxs-lookup"><span data-stu-id="e0c32-102">IdxToUnitary function</span></span>

<span data-ttu-id="e0c32-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e0c32-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e0c32-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0c32-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0c32-105">Usado na implementação de `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="e0c32-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e0c32-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e0c32-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="e0c32-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e0c32-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="e0c32-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e0c32-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtounitary--generatorindex---qubit--unit-adj--ctl"></a><span data-ttu-id="e0c32-109">genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="e0c32-109">genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="e0c32-110">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="e0c32-110">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="e0c32-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e0c32-111">See Also</span></span>

- [<span data-ttu-id="e0c32-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="e0c32-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)