---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Função dividida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845549"
---
# <a name="partitioned-function"></a>Função dividida

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Divide uma matriz em várias partes.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Entrada

### <a name="nelements--int"></a>nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]

Número de elementos em cada parte da matriz


### <a name="arr--t"></a>arr : 'T]]

Matriz de entrada a ser dividida.



## <a name="output--t"></a>Saída : 'T[][]

Múltiplas matrizes onde a primeira matriz é a primeira `nElements[0]` e a segunda matriz são as `arr` `nElements[1]` próximas `arr` etc. A última matriz conterá todos os elementos restantes.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="example"></a>Exemplo

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```