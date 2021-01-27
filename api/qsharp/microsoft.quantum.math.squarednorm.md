---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Função SquaredNorm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848222"
---
# <a name="squarednorm-function"></a>Função SquaredNorm

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a norma quadrada de 2 de um vetor.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Descrição

Devolve a 2-norma quadrada de um vetor; ou seja, dada uma entrada $\vec{x}$, devolve $\sum_i x_i^2$.

## <a name="input"></a>Entrada

### <a name="array--double"></a>matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

O vetor cujo quadrado 2-norma é para ser devolvido.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

A norma de 2 000 quadrados de `array` .