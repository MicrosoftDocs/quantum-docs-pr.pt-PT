---
uid: Microsoft.Quantum.Math.ArgComplex
title: Função ArgComplex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723268"
---
# <a name="argcomplex-function"></a>Função ArgComplex

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Devolve a fase de um número complexo de tipos `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Entrada

### <a name="input--complex"></a>entrada : [Complexo](xref:Microsoft.Quantum.Math.Complex)

Número complexo $c = x + i y$.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Fase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (\pi,\pi]$.