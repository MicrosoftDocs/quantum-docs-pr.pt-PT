---
uid: Microsoft.Quantum.Canon.CControlledCA
title: Função CControlledCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 740461ee17bdda281a6bd8572a15d27b17be9535
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840958"
---
# <a name="ccontrolledca-function"></a>Função CControlledCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira. Se `false` nada acontecer.
O modificador `CA` indica que a operação é controlável e adjacente.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj--ctl"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação a ser aplicada condicionalmente.



## <a name="output--boolt--unit--is-adj--ctl"></a>Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma nova operação que é operação se a parte de controlo clássico for verdadeira.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.CControlled](xref:Microsoft.Quantum.Canon.CControlled)