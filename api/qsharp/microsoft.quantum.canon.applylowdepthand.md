---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: AplicarDeptheoperação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841708"
---
# <a name="applylowdepthand-operation"></a>AplicarDeptheoperação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inverte um dado qubit de alvo se e somente se ambos os qubits de controlo estiverem no estado 1, com profundidade T 1, utilizando a medição para efetuar a operação adjacente.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Inverta `target` se e somente se ambos os controlos forem 1, mas assume que `target` está no estado 0.  A operação tem contagem T 4, profundidade T 1 e requer um qubit de ajudante, podendo, portanto, ser preferível a uma operação CCNOT, se `target` se sabe que é 0.  O adjacente desta operação é baseado em medição e não requer portões T, e nenhum qubit ajudante.

## <a name="input"></a>Entrada

### <a name="control1--qubit"></a>controle1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Primeiro qubit de controlo


### <a name="control2--qubit"></a>controlo2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo qubit de controlo


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auxiliar de destino; deve estar no estado 0



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- Cody Jones: "Novas construções para o portão toffoli tolerante a falhas", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328
- Peter Selinger: "Circuitos quânticos de profundidade T um", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302