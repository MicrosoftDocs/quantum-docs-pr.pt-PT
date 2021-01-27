---
uid: Microsoft.Quantum.Canon.Bound
title: Função vinculada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841059"
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

## <a name="example"></a>Exemplo

Os seguintes são equivalentes:

```qsharp
let bound = Bound([U, V]);
bound(x);
```

e

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft.Quantum.Canon.Bounda](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft.Quantum.Canon.BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)