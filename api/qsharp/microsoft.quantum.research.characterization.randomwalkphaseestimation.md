---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Operação RandomWalkPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710877"
---
# <a name="randomwalkphaseestimation-operation"></a>Operação RandomWalkPhaseEstimation

Espaço de nome: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)

Pacote: [](https://nuget.org/packages/)


Executa a estimativa da fase iterativa usando uma caminhada aleatória até aproximadamente a inferência bayesiana sobre os resultados clássicos da medição de um dado oráculo e eigenstate.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Entrada

### <a name="initialmean--double"></a>inicialMean : [Duplo](xref:microsoft.quantum.lang-ref.double)

Média da distribuição prévia normal inicial acima de $\phi$.


### <a name="initialstddev--double"></a>initialStdDev : [Duplo](xref:microsoft.quantum.lang-ref.double)

Desvio padrão da distribuição prévia normal inicial acima de $\phi$.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

Número de medições a aceitar na estimativa posterior final.


### <a name="maxmeasurements--int"></a>maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)

Número total de medições que podem ser efetuadas antes da operação ser considerada como tendo falhado.


### <a name="unwind--int"></a>desenrolar : [Int](xref:microsoft.quantum.lang-ref.int)

Número de resultados para esquecer quando os controlos de consistência falham.


### <a name="oracle--continuousoracle"></a>oráculo : [Continuarocle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Uma operação que representa um $U$ unitário de tal forma que $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ para eigenstates $\ket{\phi}$ com fase desconhecida $\phi \in \mathbb{R}+$.


### <a name="targetstate--qubit"></a>targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo em que $U$ atua.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

A estimativa final $\hat{\phi} \mathrel{:=} \expect[\phi]$ , onde a expectativa é superior ao posterior dado todos os dados aceites.

## <a name="remarks"></a>Observações

### <a name="iterative-phase-estimation-and-eigenstates"></a>Estimativa de Fase Iterativa e Estados Eigen

Em geral, o registo de entradas `eigenstate` não precisa de ser um eigenstate $\ket{\phi}$ de $U$, mas pode ser uma superposição sobre eigenstates. Suponha que o estado de entrada é dado por \start{align} \ket{\psi} & = \soma \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align} onde $ \{ \alpha \_ j $ são \} coeficientes complexos tais que $\sum \_ j \alpha \_ j^2 = 1$ e onde $U\ket{\phi \_ j} = \phi \_ j\ket{\phi \_ j}$.

Em seguida, a realização de estimativas de fase iterativas irá eventualmente convergir para um único eigenstate, como descrito no guia de [desenvolvimento](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).

### <a name="experiment-design"></a>Design de experiências

Os tempos de medição $t$ e os ângulos de inversão $\theta$ `oracle` passados são escolhidos de acordo com o *palpite de partícula heurístico* , \start{align} \theta \sim \Pr(\phi),\quad t \approx \frac {1} {\variance{\phi}}
\end{align} Este heurístico é ótimo para reduzir a variação posterior esperada na estimativa de fase iterativa sob o pressuposto de um prior normal.

### <a name="optimality"></a>Optimalidade

Esta operação aproxima o estimador ideal para a fase $\phi$, tal como avaliado com a perda quadrática $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.

Consulte [a Estimativa da Fase Bayesiana](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) para obter mais detalhes sobre as estatísticas da estimativa da fase iterativa.

## <a name="references"></a>Referências

- Ferrie *et al.* 2011 [doi:10/tfx,](https://doi.org/10.1007/s11128-012-0407-6) [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe e Granade 2018 *(em preparação)* .