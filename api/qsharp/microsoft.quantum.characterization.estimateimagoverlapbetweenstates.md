---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimativaImagOverlapBetweenStates operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: b192abc4ba37d126bf46f94c66cb87fe3bbec4c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216205"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>EstimativaImagOverlapBetweenStates operação

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tendo em conta duas operações que cada uma prepara cópias de um Estado, estima a parte imaginária da sobreposição entre os Estados preparados por cada operação.

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="commonpreparation--qubit--unit--is-adj"></a>comunsPreparação : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Uma operação que prepara um estado de entrada fixo.


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparação1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

A primeira das duas operações de preparação do Estado a ser comparada.


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparação2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

A segunda das duas operações de preparação do Estado deve ser comparada.


### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que `commonPreparation` `preparation1` , e todos `preparation2` agem.


### <a name="nmeasurements--int"></a>n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)

O número de medições a utilizar na estimativa da sobreposição.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observações

Esta operação usa o teste Hadamard para encontrar a parte imaginária de $$ \start{align} \braket{\psi V^{\dagger} U / \psi} \end{align} $$ where $\ket{\psi}$ é o estado preparado `commonPreparation` por, $U$ é a representação unitária da ação de `preparation1` , e onde $V$ corresponde a `preparation2` .

## <a name="references"></a>Referências

- Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)