---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Função IsSorted
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719099"
---
# <a name="issorted-function"></a>Função IsSorted

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz, devolve se essa matriz é classificada como definida por uma determinada função de comparação.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrada

### <a name="comparison--tt---bool"></a>comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função que compara dois elementos tais que `a` são considerados inferiores ou iguais a `b` se for `comparison(a, b)` `true` .


### <a name="array--t"></a>matriz : 'T[]

A matriz a ser verificada.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` se e somente se para cada par de elementos `a` e de ocorrer por esta `b` `array` ordem, é `comparison(a, b)` `true` .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `array` .

## <a name="remarks"></a>Observações

A função `comparison` é assumida como transitiva, de tal forma que se `comparison(a, b)` e , `comparison(b, c)` `comparison(a, c)` então, é assumido. Se esta propriedade não tiver, então a saída desta função pode estar incorreta.