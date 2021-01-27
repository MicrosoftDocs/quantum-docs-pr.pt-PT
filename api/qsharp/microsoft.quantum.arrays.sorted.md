---
uid: Microsoft.Quantum.Arrays.Sorted
title: Função ordenada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845450"
---
# <a name="sorted-function"></a>Função ordenada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma matriz, devolve os elementos dessa matriz classificados por uma determinada função de comparação.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="comparison--tt---bool"></a>comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função que compara dois elementos tais que `a` são considerados inferiores ou iguais a `b` se for `comparison(a, b)` `true` .


### <a name="array--t"></a>matriz : 'T[]

A matriz a ser ordenada.



## <a name="output--t"></a>Saída : 'T].



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `array` .

## <a name="example"></a>Exemplo

O seguinte corte ordena uma matriz de inteiros a ocorrer por ordem crescente:

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>Observações

A função `comparison` é assumida como transitiva, de tal forma que se `comparison(a, b)` e , `comparison(b, c)` `comparison(a, c)` então, é assumido. Se esta propriedade não tiver, então a saída desta função pode estar incorreta.

Como esta é uma função, os resultados são completamente determináveis, mesmo quando dois elementos são considerados iguais `comparison` em; isto é, quando `comparison(a, b)` e são `comparison(b, a)` `true` ambos.
Em particular, o tipo desempenhado por esta função é garantido ser estável, de modo que se dois elementos `a` e `b` ocorrerem nessa ordem dentro `array` e forem considerados iguais em , `comparison` `a` então também aparecerá antes `b` na saída.

Por exemplo:

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```