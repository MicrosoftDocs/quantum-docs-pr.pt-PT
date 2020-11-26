---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: Função IdênticoPointPosFactFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223056"
---
# <a name="identicalpointposfactfxp-function"></a>Função IdênticoPointPosFactFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Afirma que todos os números de pontos fixos na matriz fornecida têm posições de ponto idênticas quando contam a partir da parte menos significativa. Ou seja, o número de bits menos posição de ponto deve ser constante para todos os números de ponto fixo na matriz.

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="fixedpoints--fixedpoint"></a>pontos fixos : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

Matriz de números de pontos fixos quânticos que serão verificados para compatibilidade (usando afirmações).



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

