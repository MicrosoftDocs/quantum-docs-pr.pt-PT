---
uid: Microsoft.Quantum.Canon.Angle
title: Função de ângulo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718487"
---
# <a name="angle-function"></a>Função de ângulo

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Devoluções 1, se `index` tiver um número ímpar de 1s e -1, se tiver um número par de `index` 1s.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Descrição

O valor corresponde ao sinal do coeficiente do espectro Rademacher-Walsh da função n-variável E para uma determinada atribuição que decide o ângulo da rotação.

## <a name="input"></a>Entrada

### <a name="index--int"></a>índice : [Int](xref:microsoft.quantum.lang-ref.int)

Atribuição de entrada como inteiro (de 0 a 2^n - 1)



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

