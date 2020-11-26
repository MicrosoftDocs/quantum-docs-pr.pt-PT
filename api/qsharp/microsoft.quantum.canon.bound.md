---
uid: Microsoft.Quantum.Canon.Bound
title: Função vinculada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207603"
---
# <a name="bound-function"></a>Função vinculada

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit-"></a>operações : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> []

Uma sequência de operações a realizar numa dada entrada.



## <a name="output--t--unit"></a>Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma nova operação que executa cada operação em sequência na sua entrada.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo em que cada uma das operações na matriz atuam.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft.Quantum.Canon.Bounda](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft.Quantum.Canon.BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)