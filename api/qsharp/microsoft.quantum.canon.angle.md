---
uid: Microsoft.Quantum.Canon.Angle
title: Função de ângulo
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219418"
---
# <a name="angle-function"></a>Função de ângulo

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devoluções 1, se `index` tiver um número ímpar de 1s e -1, se tiver um número par de `index` 1s.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Description

O valor corresponde ao sinal do coeficiente do espectro Rademacher-Walsh da função n-variável E para uma determinada atribuição que decide o ângulo da rotação.

## <a name="input"></a>Entrada

### <a name="index--int"></a>índice : [Int](xref:microsoft.quantum.lang-ref.int)

Atribuição de entrada como inteiro (de 0 a 2^n - 1)



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

