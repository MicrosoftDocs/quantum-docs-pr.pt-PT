---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: Preparar operaçãoArbitraryStateD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 61f6614821951435828cd28edeb1447cb33f3648
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842362"
---
# <a name="preparearbitrarystated-operation"></a>Preparar operaçãoArbitraryStateD

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um conjunto de coeficientes e um pequeno registo quântico codificado, prepara um estado nesse registo descrito pelos coeficientes.

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0 \cdots 0}$.
Em particular, a ação desta operação pode ser simulada pela transformação unitária $U$ que atua no estado de todos os zeros como

$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\ \\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{{j} \{sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.
\end{align} $$

## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Matriz de até $2^n$ coeficientes reais. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O número de codificação do registo qubit está em formato pouco endiano. Espera-se que isto seja inicializado na base computacional do estado $\ket{0...0}$.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Coeficientes de entrada negativos $r_j < 0$ serão tratados como positivos com valor de $|r_j|$. `coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .

## <a name="references"></a>Referências

- Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.ApproximatePrepareArbitraryState](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)