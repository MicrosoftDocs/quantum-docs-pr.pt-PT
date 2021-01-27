---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Função ConstantArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846233"
---
# <a name="constantarray-function"></a>Função ConstantArray

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cria uma matriz de comprimento dado com todos os elementos iguais ao valor dado.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="length--int"></a>comprimento : [Int](xref:microsoft.quantum.lang-ref.int)

Comprimento da nova matriz.


### <a name="value--t"></a>valor : 'T

O valor de cada elemento da nova matriz.



## <a name="output--t"></a>Saída : 'T].

Uma nova matriz de `length` comprimento, de tal forma que cada elemento é `value` .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="example"></a>Exemplo

O seguinte código cria uma matriz de 3 valores booleanas, cada um igual `true` a:

```qsharp
let array = ConstantArray(3, true);
```