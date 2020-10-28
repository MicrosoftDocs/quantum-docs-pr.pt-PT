---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: Função ColumnAtUnchecked
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719447"
---
# <a name="columnatunchecked-function"></a>Função ColumnAtUnchecked

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Esta função não verifica a forma da matriz

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descrição

Esta função pode ser utilizada noutras funções multidimensionais, que já verificam a matriz de entrada para uma forma retangular válida.

## <a name="input"></a>Entrada

### <a name="column--int"></a>coluna : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="matrix--t"></a>matriz : 'T[][]





## <a name="output--t"></a>Saída : 'T].



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

