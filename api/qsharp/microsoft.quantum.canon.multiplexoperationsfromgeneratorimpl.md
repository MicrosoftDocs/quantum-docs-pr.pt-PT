---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGeneratorImpl
title: Operação MultiplexOperationsFromGeneratorImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGeneratorImpl
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 68c9fcf7ee7893dc3ef6600cc5d6c5be807f9eb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852475"
---
# <a name="multiplexoperationsfromgeneratorimpl-operation"></a><span data-ttu-id="c3570-102">Operação MultiplexOperationsFromGeneratorImpl</span><span class="sxs-lookup"><span data-stu-id="c3570-102">MultiplexOperationsFromGeneratorImpl operation</span></span>

<span data-ttu-id="c3570-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3570-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3570-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3570-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3570-105">Passo de implementação de `MultiplexOperationsFromGenerator` .</span><span class="sxs-lookup"><span data-stu-id="c3570-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation MultiplexOperationsFromGeneratorImpl<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c3570-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c3570-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit--is-adj--ctl"></a><span data-ttu-id="c3570-107">unitárioGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span><span class="sxs-lookup"><span data-stu-id="c3570-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="c3570-108">auxiliar : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3570-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="c3570-109">índice : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c3570-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="c3570-110">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="c3570-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="c3570-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3570-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c3570-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c3570-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3570-113">'T</span><span class="sxs-lookup"><span data-stu-id="c3570-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="c3570-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c3570-114">See Also</span></span>

- [<span data-ttu-id="c3570-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="c3570-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)