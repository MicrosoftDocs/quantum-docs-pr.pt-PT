---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: Decompondo a funçãoIntoTimeStepsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: 4443af5884755f72fac6f9b76f95c3831c67b13f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207178"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="eedfb-102">Decompondo a funçãoIntoTimeStepsCA</span><span class="sxs-lookup"><span data-stu-id="eedfb-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="eedfb-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eedfb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eedfb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eedfb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="eedfb-105">DecompeIntoTimeStepsCA foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="eedfb-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="eedfb-106">Por favor, use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="eedfb-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="eedfb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="eedfb-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="eedfb-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eedfb-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="eedfb-109">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="eedfb-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="eedfb-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eedfb-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="eedfb-111">Saída :[(Duplo](xref:microsoft.quantum.lang-ref.double),'T) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="eedfb-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eedfb-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="eedfb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eedfb-113">'T</span><span class="sxs-lookup"><span data-stu-id="eedfb-113">'T</span></span>

