---
uid: Microsoft.Quantum.Canon.CControlledCA
title: Função CControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716572"
---
# <a name="ccontrolledca-function"></a>Função CControlledCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira. Se `false` nada acontecer.
O modificador `CA` indica que a operação é controlável e adjacente.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl--adj"></a>op : 'T = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit) + Adj

Uma operação a ser aplicada condicionalmente.



## <a name="output--boolt--unit-ctl--adj"></a>Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj

Uma nova operação que é operação se a parte de controlo clássico for verdadeira.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.CControlled](xref:Microsoft.Quantum.Canon.CControlled)