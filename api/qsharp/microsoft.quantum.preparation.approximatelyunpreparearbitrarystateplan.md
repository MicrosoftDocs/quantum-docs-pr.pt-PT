---
uid: Microsoft.Quantum.Preparation.ApproximatelyUnprepareArbitraryStatePlan
title: Função AproximadamenteUnprepareArbitraryStatePlan
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: d506e3a8bff365f1c99d4ed1eb41d29ba3dbeb18
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842428"
---
# <a name="approximatelyunpreparearbitrarystateplan-function"></a>Função AproximadamenteUnprepareArbitraryStatePlan

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Passo de implementação do procedimento arbitrário de preparação do Estado.

```qsharp
function ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)




### <a name="coefficients--complexpolar"></a>coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="rngcontrol--range"></a>rngControl : [Gama](xref:microsoft.quantum.lang-ref.range)




### <a name="idxtarget--int"></a>idxTarget : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubit--unit--is-adj--ctl"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl[]



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.PrepareArbitraryState](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [Microsoft.Quantum.Canon.MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)