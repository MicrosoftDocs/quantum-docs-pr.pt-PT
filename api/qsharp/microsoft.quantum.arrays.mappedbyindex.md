---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: Função MapedByIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719051"
---
# <a name="mappedbyindex-function"></a>Função MapedByIndex

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz e uma função que é definida para os elementos indexados da matriz, devolve uma nova matriz que consiste nas imagens da matriz original sob a função.

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrada

### <a name="mapper--intt---u"></a>mapper :[(Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U

Uma função disso `(Int, 'T)` `'U` é usada para mapear elementos e seus índices.


### <a name="array--t"></a>matriz : 'T[]

Uma série de elementos sobre `'T` .



## <a name="output--u"></a>Saída : 'U].

Uma matriz `'U[]` de elementos que são mapeados pela `mapper` função.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.
### <a name="u"></a>'U

O tipo de resultado da `mapper` função.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Mapeado](xref:Microsoft.Quantum.Arrays.Mapped)