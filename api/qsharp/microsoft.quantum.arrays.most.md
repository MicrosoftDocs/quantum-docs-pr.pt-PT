---
uid: Microsoft.Quantum.Arrays.Most
title: A maioria da função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845587"
---
# <a name="most-function"></a>A maioria da função

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cria uma matriz que é igual a uma matriz de entrada, exceto que o último elemento de matriz é largado.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz : 'T[]

Uma matriz cujos primeiros e últimos elementos são para formar a matriz de saída.



## <a name="output--t"></a>Saída : 'T].

Uma matriz contendo os `array[0..Length(array) - 2]` elementos.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos de matriz.