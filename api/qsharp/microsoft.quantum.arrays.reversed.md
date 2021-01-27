---
uid: Microsoft.Quantum.Arrays.Reversed
title: Função invertida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845462"
---
# <a name="reversed-function"></a>Função invertida

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crie uma matriz que contenha os mesmos elementos que uma matriz de entrada, mas em ordem invertida.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz : 'T[]

Uma matriz cujos elementos devem ser copiados por ordem inversa.



## <a name="output--t"></a>Saída : 'T].

Uma matriz contendo os `array[Length(array) - 1]` elementos.. `array[0]`.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos de matriz.