---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Função dividida
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220506"
---
# <a name="partitioned-function"></a>Função dividida

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Divide uma matriz em várias partes.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Entrada

### <a name="nelements--int"></a>nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]

Número de elementos em cada parte da matriz


### <a name="arr--t"></a>arr : 'T]]

Matriz de entrada a ser dividida.



## <a name="output--t"></a>Saída : 'T[][]

Múltiplas matrizes onde a primeira matriz é a primeira `nElements[0]` e a segunda matriz são as `arr` `nElements[1]` próximas `arr` etc. A última matriz conterá todos os elementos restantes.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

