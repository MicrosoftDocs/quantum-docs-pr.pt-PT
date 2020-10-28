---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Função dividida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718978"
---
# <a name="partitioned-function"></a>Função dividida

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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

