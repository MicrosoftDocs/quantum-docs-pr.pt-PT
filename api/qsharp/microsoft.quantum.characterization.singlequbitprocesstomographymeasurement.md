---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operação singleQubitProcessTomographyMeasurement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 3756040df8e34ecee1e968428b08387e0096ab7b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204203"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>Operação singleQubitProcessTomographyMeasurement

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza uma medição de tomografia de processo de um único qubit na base Pauli, dado um determinado canal de interesse.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Entrada

### <a name="preparation--pauli"></a>preparação : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

O elemento base Pauli $P$ em que um qubit deve ser preparado.


### <a name="measurement--pauli"></a>medição : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

O elemento base Pauli $Q$ em que um qubit deve ser medido.


### <a name="channel--qubit--unit"></a>canal : [Unidade Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Um único canal qubit $\Lambda$ cujo comportamento está a ser estimado com tomografia de processo.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O Resultado `Zero` com probabilidade $$ \begin{align} \Pr (\texttt{Zero} / \Lambda; P, Q) = \operatorname{Tr}\left\ frac{\boldone + Q} {2} \Lambda\left[ \frac{\boldone + P} {2} \direita).
\end{align} $$

## <a name="remarks"></a>Observações

A distribuição sobre os resultados devolvidos por esta operação é um caso especial de tomografia estatal de dois qubits. Let $\rho = J(\Lambda) / 2$ seja o estado Choi-Jamiłkowski por $\Lambda$. Em seguida, a distribuição acima é idêntica a $$ \start{align} \Pr (\texttt{Zero} / \rho; M) = \operatorname{Tr}(M\rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ é a medida eficaz correspondente a $P$ e $Q$.