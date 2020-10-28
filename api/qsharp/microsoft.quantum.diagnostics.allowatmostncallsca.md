---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Permitir a operação DaMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713061"
---
# <a name="allowatmostncallsca-operation"></a>Permitir a operação DaMostNCallsCA

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Entre uma chamada para esta operação e o seu adjacente, afirma que uma determinada operação é chamada no máximo um certo número de vezes.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="ntimes--int"></a>nTimes : [Int](xref:microsoft.quantum.lang-ref.int)

O número máximo de vezes que `op` pode ser chamado.


### <a name="op--tinput--toutput-adj--ctl"></a>op : 'TInput => 'TOutput Adj + Ctl

Uma operação cujas chamadas devem ser restringidas.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser exibida após o fracasso.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>'TOutput



## <a name="remarks"></a>Observações

Esta operação pode ser substituída por um não-operatório sobre alvos que não a suportem.