---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimativaImagOverlapBetweenStates operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: f18ce43f9e5ebada4c5cc0aeff1538ac640c7390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851876"
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

Esta operação utiliza o teste Hadamard para encontrar a parte imaginária de $$ \start{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ é o estado preparado `commonPreparation` por, $U$ é a representação unitária da ação de `preparation1` , e onde $V$ corresponde a `preparation2` .

## <a name="references"></a>Referências

- Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)