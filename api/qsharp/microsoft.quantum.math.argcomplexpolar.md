---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: Função ArgComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852906"
---
# <a name="argcomplexpolar-function"></a>Função ArgComplexPolar

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a fase de um número complexo de tipos `ComplexPolar` .

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a>Entrada

### <a name="input--complexpolar"></a>entrada : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Número complexo $c = r e^{i t}$.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Fase $\text{Arg}[c] = t$.