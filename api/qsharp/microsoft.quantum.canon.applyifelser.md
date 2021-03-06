---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: Aplicação OperaçãoIfElseR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841799"
---
# <a name="applyifelser-operation"></a>Aplicação OperaçãoIfElseR

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma de duas operações, dependendo do valor de um resultado clássico.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Descrição

Dado o `result` resultado, aplica a operação `zeroOp` com a sua entrada quando é igual a , e `zeroInput` `result` `Zero` aplica-se `oneOp(oneInput)` quando `result == One` .

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado : __inválido <Result>__

O resultado da medição utilizado para determinar se `zeroOp` ou `oneOp` é aplicado.


### <a name="zeroop--t--unit"></a>zeroOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

A operação a aplicar quando `result == Zero` . .


### <a name="zeroinput--t"></a>zeroInput : 'T

A entrada a fornecer `zeroOp` quando `result == Zero` . .


### <a name="oneop--u--unit"></a>oneOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

A operação a aplicar quando `result == One` . .


### <a name="oneinput--u"></a>oneInput : 'U

A entrada a fornecer `oneOp` quando `result == One` . .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação `zeroOp` a aplicar condicionalmente.
### <a name="u"></a>'U

O tipo de entrada da operação `oneOp` a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft.Quantum.Canon.ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft.Quantum.Canon.ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft.Quantum.Canon.ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft.Quantum.Canon.ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)