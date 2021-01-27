---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: AplicaçãoFermionicSWAP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845056"
---
# <a name="applyfermionicswap-operation"></a>AplicaçãoFermionicSWAP

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica o Permuta Fermionic.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Isto essencialmente troca os qubits ao aplicar uma fase global de -1 se ambos os qubits forem 1s. Preserva a anti-symmetrização dos orbitais.
Consulte  para obter mais informações.

Esta operação é representada pelo operador unitário \start{align} f_{swap} \mathrel{:=} \start{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & \\ \\ 0 0 & 1 & 0 & 0 \\ \\ & 0 & 0 & -1 \\ \\ \end{bmatrix}.
\end{align}

## <a name="input"></a>Entrada

### <a name="qubit1--qubit"></a>qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O primeiro qubit a ser trocado.


### <a name="qubit2--qubit"></a>qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O segundo qubit a ser trocado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- [*Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Intrínseco.SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)