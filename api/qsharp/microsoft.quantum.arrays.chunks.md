---
uid: Microsoft.Quantum.Arrays.Chunks
title: Função de pedaços
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719470"
---
# <a name="chunks-function"></a>Função de pedaços

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Divide uma matriz em várias partes de comprimento igual.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Entrada

### <a name="nelements--int"></a>nElements : [Int](xref:microsoft.quantum.lang-ref.int)

O comprimento de cada pedaço.


### <a name="arr--t"></a>arr : 'T]]

A matriz a ser dividida.



## <a name="output--t"></a>Saída : 'T[][]

Uma matriz contendo cada pedaço da matriz original.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

Note que o último elemento da saída pode ser mais curto do que `nElements` se `Length(arr)` não for divisível por `nElements` .