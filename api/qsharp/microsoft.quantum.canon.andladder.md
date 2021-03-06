---
uid: Microsoft.Quantum.Canon.AndLadder
title: E Operação ELadder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845229"
---
# <a name="andladder-operation"></a>E Operação ELadder

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa uma "escada" controlada num registo de qubits-alvo.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a>Descrição

Esta operação aplica uma transformação descrita pelo seguinte mapeamento da base computacional, $$ \start{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \pontos, y \_ {n - 1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{ \_ y 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n - 1} \oplus (x \_ 1 \land x \_ 2 \land \land x \_ {n - 1} }, \end{align} $$ where $\ket{x \_ 1, \dots, x \_ n}$ refere-se aos estados de base computacional de `controls` , e onde $\ket{y \_ 1, \dots, y \_ {n - 1}}$ refere-se aos estados de base computacional de `targets` .

## <a name="input"></a>Entrada

### <a name="ccnot--ccnotop"></a>ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

O portão CCNOT para usar para a construção.


### <a name="controls--qubit"></a>controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits a utilizar como controlos para a escada e escada.
Esta operação deixa estados de base computacional `controls` invariantes.
O comprimento `controls` deve ser de, pelo menos, 2, e deve ser igual a um mais o comprimento de `targets` .


### <a name="targets--qubit"></a>alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

O comprimento `targets` deve ser de, pelo menos, 1 e igual ao comprimento de `controls` menos um.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

- Usado como parte de <xref:microsoft.quantum.canon.applymulticontrolledc> e <xref:microsoft.quantum.canon.applymulticontrolledca> .
- Para a explicação e diagrama do circuito consulte a Figura 4.10, Secção 4.3 em Nielsen & Chuang.

## <a name="references"></a>Referências

- [*Michael A. Nielsen , Isaac L. Chuang,* Quantum Computation e Quantum Information](http://doi.org/10.1017/CBO9780511976667)