---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: Função QuantumWalkByQubitization
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851060"
---
# <a name="quantumwalkbyqubitization-function"></a>Função QuantumWalkByQubitization

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte uma reflexão de codificação de blocos numa caminhada quântica.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descrição

Dado um `BlockEncodingReflection` representado por um $U$ unitário que codifica algum operador $H$ de juros, converte-o numa caminhada quântica $W$ contendo o espectro de $\pm e^\pm i\sin^ {-1} (H)}$.

## <a name="input"></a>Entrada

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Um `BlockEncodingReflection` $U unitário para ser convertido numa caminhada quântica.



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Uma caminhada quântica $W$ agindo conjuntamente em registos `a` e que codifica o `s` $H$, e contém o espectro de $\pm e^{\pm i\sin^ {-1} (H)}$.

## <a name="references"></a>Referências

- Simulação Hamiltonian por Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft.Quantum.Simulation.BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)