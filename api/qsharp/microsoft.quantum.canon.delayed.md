---
uid: Microsoft.Quantum.Canon.Delayed
title: Função atrasada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216460"
---
# <a name="delayed-function"></a>Função atrasada

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação que se aplica a uma determinada operação com um argumento dado.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Entrada

### <a name="op--t--u"></a>op : 'T => 'U 

Uma operação a ser aplicada.


### <a name="arg--t"></a>arg : 'T

A entrada à qual a operação é aplicada.



## <a name="output--unit--u"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit) => 'U 

Uma nova operação que se aplica `op` com a entrada `arg`

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a ser adiado.
### <a name="u"></a>'U

O tipo de retorno da operação a ser adiado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft.Quantum.Canon.Delayeda](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft.Quantum.Canon.DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft.Quantum.Canon.Delay](xref:Microsoft.Quantum.Canon.Delay)