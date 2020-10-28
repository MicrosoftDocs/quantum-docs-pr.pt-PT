---
uid: Microsoft.Quantum.Arrays.Unique
title: Função única
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718786"
---
# <a name="unique-function"></a>Função única

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Devolve uma nova matriz que não tem elementos adjacentes iguais.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Descrição

Dada a variedade de elementos e uma função para testar a igualdade, esta função devolve uma nova matriz na qual a ordem relativa dos elementos é mantida, mas todos os elementos adjacentes que são iguais são filtrados a apenas um elemento.

## <a name="input"></a>Entrada

### <a name="equal--tt---bool"></a>igual: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função que compara dois elementos tais que `a` são considerados iguais a `b` se `equal(a, b)` for `true` .


### <a name="array--t"></a>matriz : 'T[]

A matriz a ser filtrada para elementos únicos.



## <a name="output--t"></a>Saída : 'T].

Matriz sem elementos adjacentes iguais.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `array` .

## <a name="remarks"></a>Observações

Se houver vários elementos iguais, mas não próximos uns dos outros, haverá múltiplas ocorrências na matriz de saída.  Utilize esta função juntamente com `Sorted` para obter uma matriz com elementos únicos em geral.