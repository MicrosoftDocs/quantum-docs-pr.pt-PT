---
uid: Microsoft.Quantum.Canon.CControlled
title: Função CControled
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841015"
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