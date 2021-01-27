---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: Função BoolArrayAsResultArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834196"
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