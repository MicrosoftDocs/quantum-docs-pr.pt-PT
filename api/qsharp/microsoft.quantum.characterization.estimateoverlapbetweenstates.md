---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimativasOverlapBetweenStates operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714993"
---
# <a name="estimateoverlapbetweenstates-operation"></a>EstimativasOverlapBetweenStates operação

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [](https://nuget.org/packages/)


Tendo em conta duas operações que cada uma prepara cópias de um Estado, estima a sobreposição quadrada entre os Estados preparados por cada operação.

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="preparation1--qubit--unit-adj"></a>preparação1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj

A primeira das duas operações de preparação do Estado a ser comparada.


### <a name="preparation2--qubit--unit-adj"></a>preparação2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj

A segunda das duas operações de preparação do Estado deve ser comparada.


### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que `commonPreparation` `preparation1` , e todos `preparation2` agem.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de medições a utilizar na estimativa da sobreposição.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observações

Esta operação utiliza o teste SWAP para encontrar $$ \start{align} \left/ \braket{00\cdots 0 / V^{\dagger} U / 00\cdots 0} \direita/^2 \end{} $$ onde $U$ é a representação unitária da ação de `preparation1` , e onde $V$ corresponde a `preparation2` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)