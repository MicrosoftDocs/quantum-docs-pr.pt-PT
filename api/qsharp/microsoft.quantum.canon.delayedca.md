---
uid: Microsoft.Quantum.Canon.DelayedCA
title: Função DeDCA atrasada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: c44e3448c471f2a20f995d4546ee54f3affb726e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840557"
---
# <a name="delayedca-function"></a>Função DeDCA atrasada

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação que se aplica a uma determinada operação com um argumento dado.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj--ctl"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação a aplicar como resultado da aplicação do valor de retorno


### <a name="arg--t"></a>arg : 'T

A entrada à qual a operação `op` é aplicada.



## <a name="output--unit--unit--is-adj--ctl"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit) => [unitária](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Uma nova operação que se aplica `op` com a entrada `arg`

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a ser adiado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Adiado](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft.Quantum.Canon.Delay](xref:Microsoft.Quantum.Canon.Delay)