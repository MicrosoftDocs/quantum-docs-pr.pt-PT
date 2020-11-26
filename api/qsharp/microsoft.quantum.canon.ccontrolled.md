---
uid: Microsoft.Quantum.Canon.CControlled
title: Função CControled
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: 76e663e9a4b53c7ed74a1b70da516fb07958923b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216901"
---
# <a name="ccontrolled-function"></a>Função CControled

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira. Se `false` nada acontecer.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser aplicada condicionalmente.



## <a name="output--boolt--unit"></a>Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma nova operação que é operação se a parte de controlo clássico for verdadeira.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft.Quantum.Canon.CControlleda](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft.Quantum.Canon.CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)