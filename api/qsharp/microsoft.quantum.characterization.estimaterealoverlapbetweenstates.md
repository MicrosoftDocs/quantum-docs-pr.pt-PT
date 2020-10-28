---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimativaRealOverlapBetweenStates operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714976"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>EstimativaRealOverlapBetweenStates operação

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [](https://nuget.org/packages/)


Tendo em conta duas operações que cada uma prepara cópias de um Estado, estima a parte real da sobreposição entre os Estados preparados por cada operação.

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="commonpreparation--qubit--unit-adj"></a>comunsPreparação : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj

Uma operação que prepara um estado de entrada fixo.


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparação1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = unidade> [Adj](xref:microsoft.quantum.lang-ref.unit) + Ctl

A primeira das duas operações de preparação do Estado a ser comparada.


### <a name="preparation2--qubit--unit-adj--ctl"></a>preparação2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl

A segunda das duas operações de preparação do Estado deve ser comparada.


### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que `commonPreparation` `preparation1` , e todos `preparation2` agem.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de medições a utilizar na estimativa da sobreposição.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observações

Esta operação usa o teste Hadamard para encontrar a parte real de $$ \start{align} \braket{\psi V^{\dagger} U / \psi} \end{align} $$ where $\ket{\psi}$ é o estado preparado `commonPreparation` por, $U$ é a representação unitária da ação de `preparation1` , e onde $V$ corresponde a `preparation2` .

## <a name="references"></a>Referências

- Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)