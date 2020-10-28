---
uid: Microsoft.Quantum.Arrays.Reversed
title: Função invertida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718907"
---
# <a name="reversed-function"></a>Função invertida

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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