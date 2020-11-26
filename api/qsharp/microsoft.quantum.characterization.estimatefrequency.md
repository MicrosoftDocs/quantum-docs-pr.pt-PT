---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Estimativa OperaçãoFrequency
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 30b21a8e86eb5a4dd8dd8207dbdc6a0970308319
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216256"
---
# <a name="estimatefrequency-operation"></a>Estimativa OperaçãoFrequency

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada a preparação e medição, estima a frequência com que essa medição sucede (devoluções) `Zero` através da realização de um determinado número de ensaios.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="preparation--qubit--unit"></a>preparação: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação $P$ que prepara um dado estado $\rho$ no seu registo de entradas.


### <a name="measurement--qubit--__invalidresult__"></a>medição: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __inválido <Result>__ 

Uma operação $M$ representando a medição de juros.


### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que a preparação e a medição de cada ato.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes que a medição deve ser efetuada para estimar a frequência de juros.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma estimativa $\hat{p}$ da frequência com a qual $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0})$ `Zero` devoluções, obtidas usando o estimador binomial imparcial $\hat{p} = \_ n{\uparrow} / \_ {{text{s}}}}}}}}}}}} onde $n \_ {\uparrow}$ é o número de `Zero` resultados observados.

Isto é particularmente importante para as máquinas-alvo que respeitam as limitações físicas, de modo a que as probabilidades não possam ser medidas.