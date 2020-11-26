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
# <a name="decomposeintotimestepsca-function"></a>Decompondo a funçãoIntoTimeStepsCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> DecompeIntoTimeStepsCA foi depreciado. Por favor, use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> em vez disso.



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="nsteps--int"></a>nSteps : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--intdoublet--unit--is-adj--ctl"></a>op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl




### <a name="trotterorder--int"></a>trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--doublet--unit--is-adj--ctl"></a>Saída :[(Duplo](xref:microsoft.quantum.lang-ref.double),'T) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

