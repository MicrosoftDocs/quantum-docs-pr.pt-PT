---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Função SquaredNorm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227306"
---
# <a name="squarednorm-function"></a>Função SquaredNorm

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a norma quadrada de 2 de um vetor.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Description

Devolve a 2-norma quadrada de um vetor; ou seja, dada uma entrada $\vec{x}$, devolve $\sum_i x_i^2$.

## <a name="input"></a>Entrada

### <a name="array--double"></a>matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

O vetor cujo quadrado 2-norma é para ser devolvido.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

A norma de 2 000 quadrados de `array` .