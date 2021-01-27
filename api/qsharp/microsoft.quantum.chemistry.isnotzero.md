---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Função IsNotZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839605"
---
# <a name="isnotzero-function"></a>Função IsNotZero

Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Verifica se um `Double` número não é aproximadamente zero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Entrada

### <a name="number--double"></a>número : [Duplo](xref:microsoft.quantum.lang-ref.double)

Número a ser verificado



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

Retorna verdadeira se `number` tiver um valor absoluto superior a `1e-15` .