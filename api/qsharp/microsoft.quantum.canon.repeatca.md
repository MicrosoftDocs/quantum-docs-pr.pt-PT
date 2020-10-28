---
uid: Microsoft.Quantum.Canon.RepeatCA
title: Operação RepeatCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715550"
---
# <a name="repeatca-operation"></a>Operação RepeatCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Repete uma operação um dado número de vezes.

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--tinput--unit-adj--ctl"></a>op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

A operação a ser convocada repetidamente.


### <a name="ntimes--int"></a>nTimes : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes para `op` ligar.


### <a name="input--tinput"></a>entrada : 'TInput

A entrada a passar para `op` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="tinput"></a>'TInput



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.DrawMany](xref:Microsoft.Quantum.Arrays.DrawMany)
- [Microsoft.Quantum.Canon.Repeat](xref:Microsoft.Quantum.Canon.Repeat)
- [Microsoft.Quantum.Canon.Repeata](xref:Microsoft.Quantum.Canon.RepeatA)
- [Microsoft.Quantum.Canon.RepeatC](xref:Microsoft.Quantum.Canon.RepeatC)