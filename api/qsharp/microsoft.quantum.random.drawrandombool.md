---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operação DrawRandomBool
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192966"
---
# <a name="drawrandombool-operation"></a>Operação DrawRandomBool

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dada a probabilidade de sucesso, devolve um único ensaio de Bernoulli que é verdade com a probabilidade dada.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="successprobability--double"></a>sucessoProbabilidade : [Duplo](xref:microsoft.quantum.lang-ref.double)

A probabilidade com que `true` deve ser devolvida.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` com probabilidade `successProbability` e `false` com `1.0 - successProbability` probabilidade.