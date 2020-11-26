---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: Função BoolArrayAsResultArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224467"
---
# <a name="boolarrayasresultarray-function"></a>Função BoolArrayAsResultArray

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte um `Bool[]` tipo para um `Result[]` tipo, onde é `true` mapeado `One` e `false` mapeado para `Zero` .

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>Entrada

### <a name="input--bool"></a>entrada : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` para ser convertido.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválido__[]

Um `Result[]` representante `input` do.