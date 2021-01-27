---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: Função InputEncoder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852946"
---
# <a name="inputencoder-function"></a>Função InputEncoder

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dado um conjunto de coeficientes e uma tolerância, devolve uma operação de preparação do Estado que prepara cada coeficiente como a amplitude correspondente de um estado de base computacional.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Os coeficientes devem ser codificados num estado de entrada.



## <a name="output--stategenerator"></a>Saída : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Uma operação de preparação do Estado que prepara os coeficientes dados como um estado de entrada num dado registo.