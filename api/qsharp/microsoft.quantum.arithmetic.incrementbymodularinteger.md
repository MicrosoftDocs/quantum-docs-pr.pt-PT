---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721102"
---
# <a name="incrementbymodularinteger-operation"></a>IncrementByModularInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Executa um incremento modular de um registo qubit por uma constante de inteiro.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrição

Vamos denotar `increment` por $a$, `modulus` por $N$ e inteiro codificado `target` por $y$.
Em seguida, a operação executa a seguinte transformação: \start{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Os inteiros são codificados em formato pouco endiano.

## <a name="input"></a>Entrada

### <a name="increment--int"></a>incremento : [Int](xref:microsoft.quantum.lang-ref.int)

Incremento inteiro $a$ a ser adicionado a $y$.


### <a name="modulus--int"></a>módulo : [Int](xref:microsoft.quantum.lang-ref.int)

Inteiro $N$ que mods $y + a$.


### <a name="target--littleendian"></a>alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O inteiro $y$ em `LittleEndian` formato a que `increment` $a$ é adicionado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Assume que o valor inicial do alvo é inferior a $N$ e que o incremento $a$ é inferior a $N$.
Note que <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementa a mesma operação na `PhaseLittleEndian` base.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Aithmetic.IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)