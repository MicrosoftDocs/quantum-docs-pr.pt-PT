---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateD
title: Operação AproximadamentePrepareArbitraryStateD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: a818ada509bcb34682ac1230eb508f0b71b5d019
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842457"
---
# <a name="approximatelypreparearbitrarystated-operation"></a>Operação AproximadamentePrepareArbitraryStateD

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um conjunto de coeficientes e um registo quântico codificado pouco endiano, prepara um estado nesse registo descrito pelos coeficientes dados, até uma certa tolerância de aproximação.

```qsharp
operation ApproximatelyPrepareArbitraryStateD (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0 \cdots 0}$.
Em particular, a ação desta operação pode ser simulada pela transformação unitária $U$ que atua no estado de todos os zeros como

$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\ \\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{{j} \{sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.
\end{align} $$

## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

A tolerância de aproximação a utilizar na preparação do estado.


### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Matriz de até $2^n$ coeficientes reais. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O número de codificação do registo qubit está em formato pouco endiano. Espera-se que isto seja inicializado na base computacional do estado $\ket{0...0}$.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Coeficientes de entrada negativos $r_j < 0$ serão tratados como positivos com valor de $|r_j|$. `coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .

## <a name="references"></a>Referências

- Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176