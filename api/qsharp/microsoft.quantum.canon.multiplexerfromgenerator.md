---
uid: Microsoft.Quantum.Canon.MultiplexerFromGenerator
title: Função multiplexerFromGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: b86238debe66747ba23c3b41164813594f80b27c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852555"
---
# <a name="multiplexerfromgenerator-function"></a>Função multiplexerFromGenerator

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação unitária controlada por multiplicões $U$ que aplica uma $V_j$ unitária quando controlada pelo estado do número n-qubit $\ket{j}$.

$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.

```qsharp
function MultiplexerFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a>unitárioGenerator :[(Int,](xref:microsoft.quantum.lang-ref.int)[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit) is Adj + Ctl)

Um tuple onde o primeiro elemento `Int` é o número de unitários $N$, e o segundo elemento é uma `(Int -> ('T => () is Adj + Ctl))` função que leva um inteiro $j$ em $[0,N-1]$ e produz a operação unitária $V_j$.



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a>Saída :[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl

Uma operação unitária controlada por multiplicásscimento $U$ que aplica unitários descritos por `unitaryGenerator` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)