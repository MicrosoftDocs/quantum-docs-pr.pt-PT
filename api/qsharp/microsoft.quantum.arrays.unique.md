---
uid: Microsoft.Quantum.Arrays.Unique
title: Função única
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850914"
---
# <a name="unique-function"></a>Função única

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exemplo

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Observações

Se houver vários elementos iguais, mas não próximos uns dos outros, haverá múltiplas ocorrências na matriz de saída.  Utilize esta função juntamente com `Sorted` para obter uma matriz com elementos únicos em geral.