---
uid: Microsoft.Quantum.Canon.NoOp
title: Operação NoOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205971"
---
# <a name="noop-operation"></a>Operação NoOp

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Executa a operação de identidade (no-op) num argumento.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Esta operação tem um valor de qualquer tipo e não lhe faz nada.
Isto pode ser útil sempre que se espera uma entrada de um tipo de operação, mas não devem ser tomadas medidas.
Por exemplo, se uma síndrome de correção de erros específica indicar que não ocorreu nenhum erro, `NoOp<Qubit[]>` pode ser o procedimento correto de recuperação.
Da mesma forma, se uma operação espera um procedimento de preparação do estado como entrada, `NoOp<Qubit[]>` pode ser usado para preparar o estado $\ket{0 \cdots 0}$.

## <a name="input"></a>Entrada

### <a name="input--t"></a>entrada : 'T

Um valor a ser ignorado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

Em quase todos os casos, o parâmetro do tipo `NoOp` para deve ser especificado explicitamente. Por exemplo, `NoOp<Qubit>` é idêntico a <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Intrínseco.I](xref:Microsoft.Quantum.Intrinsic.I)