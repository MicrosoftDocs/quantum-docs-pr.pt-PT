---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: Decompondo a funçãoIntoTimeStepsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716334"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="36e90-102">Decompondo a funçãoIntoTimeStepsCA</span><span class="sxs-lookup"><span data-stu-id="36e90-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="36e90-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="36e90-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="36e90-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36e90-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="36e90-105">DecompeIntoTimeStepsCA foi depreciado.</span><span class="sxs-lookup"><span data-stu-id="36e90-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="36e90-106">Por favor, use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> em vez disso.</span><span class="sxs-lookup"><span data-stu-id="36e90-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="36e90-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="36e90-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="36e90-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36e90-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="36e90-109">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="36e90-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="36e90-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36e90-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="36e90-111">Saída :[(Duplo](xref:microsoft.quantum.lang-ref.double),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="36e90-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="36e90-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="36e90-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36e90-113">'T</span><span class="sxs-lookup"><span data-stu-id="36e90-113">'T</span></span>

