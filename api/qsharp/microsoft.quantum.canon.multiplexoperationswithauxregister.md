---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Operação MultiplexOperationsWithAuxRegister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 530e78ba0c5ce6e0627177527daf2ccc56f537eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205988"
---
# <a name="multiplexoperationswithauxregister-operation"></a><span data-ttu-id="48633-102">Operação MultiplexOperationsWithAuxRegister</span><span class="sxs-lookup"><span data-stu-id="48633-102">MultiplexOperationsWithAuxRegister operation</span></span>

<span data-ttu-id="48633-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48633-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48633-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48633-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48633-105">Passo de implementação de MultiplexOperations.</span><span class="sxs-lookup"><span data-stu-id="48633-105">Implementation step of MultiplexOperations.</span></span>

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="48633-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="48633-106">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="48633-107">unitários : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl[]</span><span class="sxs-lookup"><span data-stu-id="48633-107">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="auxillaryregister--qubit"></a><span data-ttu-id="48633-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="48633-108">auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="48633-109">índice : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="48633-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="48633-110">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="48633-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="48633-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48633-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="48633-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="48633-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48633-113">'T</span><span class="sxs-lookup"><span data-stu-id="48633-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="48633-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="48633-114">See Also</span></span>

- [<span data-ttu-id="48633-115">Microsoft.Quantum.Canon.MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="48633-115">Microsoft.Quantum.Canon.MultiplexOperations</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperations)