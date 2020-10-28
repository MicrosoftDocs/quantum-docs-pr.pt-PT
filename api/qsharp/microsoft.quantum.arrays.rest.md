---
uid: Microsoft.Quantum.Arrays.Rest
title: Função de repouso
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718918"
---
# <a name="rest-function"></a>Função de repouso

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Cria uma matriz que é igual a uma matriz de entrada, exceto que o primeiro elemento de matriz é largado.

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz : 'T[]

Uma matriz cujos segundos e últimos elementos são para formar a matriz de saída.



## <a name="output--t"></a>Saída : 'T].

Uma matriz contendo os `array[1..Length(array) - 1]` elementos.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos de matriz.