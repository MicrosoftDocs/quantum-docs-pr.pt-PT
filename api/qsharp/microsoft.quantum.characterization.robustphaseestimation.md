---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operação RobustPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714937"
---
# <a name="robustphaseestimation-operation"></a>Operação RobustPhaseEstimation

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [](https://nuget.org/packages/)


Executa o robusto algoritmo de estimativa de fase quântica não iterativa para um dado oráculo `U` e eigenstate, e fornece uma única estimativa real da fase com escala de variação no limite de Heisenberg.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Entrada

### <a name="bitsprecision--int"></a>bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)

Isto fornece uma estimativa de $\phi$ com desvio padrão $\sigma \le 2\pi / 2^\text{bitsPrecision}$ usando uma série de consultas que escalam como $\sigma \le 10,7 \pi / \text{# de queries}$.


### <a name="oracle--discreteoracle"></a>oráculo : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Uma operação que implementa $U^m$ para os poderes inteiros $m$.


### <a name="targetstate--qubit"></a>targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo quântico em que $U$ atua. Se armazena um eigenstate $\ket{\phi}$ de $U$, então $U\ket{\phi} = e^{i\phi} \ket{\phi}$ por $\phi\in(\pi,\pi]$ uma fase desconhecida.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observações

No limite de um grande número de consultas, Cramer-Rao limites inferiores para o desvio padrão da estimativa de $\phi$ satisfazer $\sigma \ge 2 \pi / \text{# de consultas}$.

## <a name="references"></a>Referências

- Calibração Robusta de um Single-Qubit Gate-Set Universal através de Estimativa de Fase Robusta Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677