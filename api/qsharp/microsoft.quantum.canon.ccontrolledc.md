---
uid: Microsoft.Quantum.Canon.CControlledC
title: Função CControlledC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716575"
---
# <a name="ccontrolledc-function"></a>Função CControlledC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira. Se `false` nada acontecer.
O modificador `C` indica que a operação é controlável.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl"></a>op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl

Uma operação a ser aplicada condicionalmente.



## <a name="output--boolt--unit-ctl"></a>Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl

Uma nova operação que é operação se a parte de controlo clássico for verdadeira.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.CControlled](xref:Microsoft.Quantum.Canon.CControlled)