---
uid: Microsoft.Quantum.Canon.DelayedC
title: Função Dedesemtração
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840566"
---
# <a name="delayedc-function"></a>Função Dedesemtração

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação que se aplica a uma determinada operação com um argumento dado.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit--is-ctl"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL

Uma operação a aplicar como resultado da aplicação do valor de retorno


### <a name="arg--t"></a>arg : 'T

A entrada à qual a operação `op` é aplicada.



## <a name="output--unit--unit--is-ctl"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit) => [unitária](xref:microsoft.quantum.lang-ref.unit)  é CTL

Uma nova operação que se aplica `op` com a entrada `arg`

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a ser adiado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Adiado](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft.Quantum.Canon.Delay](xref:Microsoft.Quantum.Canon.Delay)