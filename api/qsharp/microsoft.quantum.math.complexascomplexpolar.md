---
uid: Microsoft.Quantum.Math.ComplexAsComplexPolar
title: Função ComplexAsComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexAsComplexPolar
qsharp.summary: Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.
ms.openlocfilehash: 4d7da9b2fd79c4b39494fd1746c303a6003139eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848855"
---
# <a name="complexascomplexpolar-function"></a>Função ComplexAsComplexPolar

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte um número complexo de tipos `Complex` para um número complexo de `ComplexPolar` tipos.

```qsharp
function ComplexAsComplexPolar (input : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a>Entrada

### <a name="input--complex"></a>entrada : [Complexo](xref:Microsoft.Quantum.Math.Complex)

Número complexo $c = x + i y$.



## <a name="output--complexpolar"></a>Saída : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Número complexo $c = r e^{i t}$.