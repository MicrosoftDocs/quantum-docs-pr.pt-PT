---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: Função LexographicComparison
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197589"
---
# <a name="lexographiccomparison-function"></a>Função LexographicComparison

Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma função de comparação, devolve uma nova função que lexograficamente compara duas matrizes.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Entrada

### <a name="elementcomparison--tt---bool"></a>elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função que compara dois elementos `x` `y` e retorna se `x` for inferior ou igual a `y` .



## <a name="output--tt---bool"></a>Saída : ('T],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função que compara duas matrizes `xs` `ys` e retorna se `xs` ocorrer antes ou igual a uma encomenda `ys` lexográfica.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos das matrizes sendo comparados.

## <a name="remarks"></a>Observações

A comparação lexográfica entre duas matrizes `xs` e é definida pelo seguinte `ys` procedimento. Dizemos que dois elementos `x` e `y` são equivalentes se e ambos `elementComparison(x, y)` são `elementComparison(y, x)` verdadeiros.

- Ambas as matrizes são comparadas elemento a elemento até ao primeiro par de elementos que não são equivalentes. A matriz que contém o elemento que ocorre primeiro de acordo com `elementComparison` o que ocorre primeiro na ordem lexográfica.
- Se não forem encontrados elementos inequivalentes, e uma matriz for maior que a outra, diz-se que a matriz mais curta ocorre primeiro.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Sorted](xref:Microsoft.Quantum.Arrays.Sorted)