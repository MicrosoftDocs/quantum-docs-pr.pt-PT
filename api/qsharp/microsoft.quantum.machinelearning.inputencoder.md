---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: Função InputEncoder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709754"
---
# <a name="inputencoder-function"></a>Função InputEncoder

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Dado um conjunto de coeficientes e uma tolerância, devolve uma operação de preparação do Estado que prepara cada coeficiente como a amplitude correspondente de um estado de base computacional.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Os coeficientes devem ser codificados num estado de entrada.



## <a name="output--stategenerator"></a>Saída : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Uma operação de preparação do Estado que prepara os coeficientes dados como um estado de entrada num dado registo.