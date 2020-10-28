---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719374"
---
# <a name="drawmany-operation"></a>DrawMany operação

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Repete uma operação para um determinado número de amostras, recolhendo as suas saídas numa matriz.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Entrada

### <a name="op--tinput--toutput"></a>op : 'TInput => 'TOutput 

A operação a ser convocada repetidamente.


### <a name="nsamples--int"></a>nSamples : [Int](xref:microsoft.quantum.lang-ref.int)

O número de amostras de chamadas `op` para recolher.


### <a name="input--tinput"></a>entrada : 'TInput

A entrada a passar para `op` .



## <a name="output--toutput"></a>Saída : 'TOutput[]



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Repeat](xref:Microsoft.Quantum.Canon.Repeat)