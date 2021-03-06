---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Estimativa OperaçãoFrequencyA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 6cca8dff70283e0d69441db8a5b31fb5bfb3082a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839920"
---
# <a name="estimatefrequencya-operation"></a>Estimativa OperaçãoFrequencyA

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma preparação que é adjacente e medição, estima a frequência com que essa medição sucede (devoluções) `Zero` através da realização de um determinado número de ensaios.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="preparation--qubit--unit--is-adj"></a>preparação: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Uma operação contável $P$ que prepara um dado estado $\rho$ no seu registo de entrada.


### <a name="measurement--qubit--__invalidresult__"></a>medição: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __inválido <Result>__ 

Uma operação $M$ representando a medição de juros.


### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que a preparação e a medição de cada ato.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes que a medição deve ser efetuada para estimar a frequência de juros.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma estimativa $\hat{p}$ da frequência com a qual $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0})$ `Zero` devoluções, obtidas usando o estimador binomial imparcial $\hat{p} = \_ n{\uparrow} / \_ {{text{s}} onde $n \_ {\uparrow}$ é o número de `Zero` resultados observados.

## <a name="remarks"></a>Observações

Para operações contíguas, certos pressupostos podem ser feitos tais como chamar a operação irá preparar os qubits exatamente para o mesmo estado, que permitem que as máquinas-alvo façam algumas otimizações de desempenho.