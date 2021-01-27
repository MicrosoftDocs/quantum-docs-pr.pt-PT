---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operação RobustPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851807"
---
# <a name="robustphaseestimation-operation"></a>Operação RobustPhaseEstimation

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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