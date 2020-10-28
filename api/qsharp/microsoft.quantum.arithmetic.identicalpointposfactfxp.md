---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: Função IdênticoPointPosFactFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721115"
---
# <a name="identicalpointposfactfxp-function"></a>Função IdênticoPointPosFactFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Afirma que todos os números de pontos fixos na matriz fornecida têm posições de ponto idênticas quando contam a partir da parte menos significativa. Ou seja, o número de bits menos posição de ponto deve ser constante para todos os números de ponto fixo na matriz.

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="fixedpoints--fixedpoint"></a>pontos fixos : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

Matriz de números de pontos fixos quânticos que serão verificados para compatibilidade (usando afirmações).



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

