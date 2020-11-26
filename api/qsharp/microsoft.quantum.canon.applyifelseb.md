---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: Aplicação OperaçãoIfElseB
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 55ba3bc8c3efb87ef4d550cceeeecd8052e4d8c0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209592"
---
# <a name="applyifelseb-operation"></a>Aplicação OperaçãoIfElseB

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma de duas operações, dependendo do valor de um pouco clássico.

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a>Description

Dado um `bit` pouco, aplica a operação `trueOp` com a sua entrada quando é , e `trueInput` `bit` `true` `falseOp(falseInput)` aplica-se quando `bit` é `false` .

## <a name="input"></a>Entrada

### <a name="bit--bool"></a>bit : [Bool](xref:microsoft.quantum.lang-ref.bool)

O valor booleano usado para determinar se `trueOp` é ou `falseOp` não aplicado.


### <a name="trueop--t--unit"></a>trueOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

A operação a aplicar quando `bit` é `true` .


### <a name="trueinput--t"></a>verdadeiroInput : 'T

A entrada a fornecer `trueOp` quando `bit` é `true` .


### <a name="falseop--u--unit"></a>falseOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

A operação a aplicar quando `bit` é `false` .


### <a name="falseinput--u"></a>falseInput : 'U

A entrada a fornecer `falseOp` quando `bit` é `false` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação `trueOp` a aplicar condicionalmente.
### <a name="u"></a>'U

O tipo de entrada da operação `falseOp` a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft.Quantum.Canon.ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft.Quantum.Canon.ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft.Quantum.Canon.ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft.Quantum.Canon.ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)