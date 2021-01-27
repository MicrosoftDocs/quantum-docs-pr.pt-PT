---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: Preparar Operação Do Estado De Preparação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: e2e4818e5d30b17dd1984c36da92d76b84403e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842389"
---
# <a name="preparearbitrarystate-operation"></a>Preparar Operação Do Estado De Preparação

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Preparerá o Estado foi depreciado. Por favor, use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> em vez disso.

Dado um conjunto de coeficientes e um pequeno registo quântico codificado, prepara um estado nesse registo descrito pelos coeficientes.

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0 \cdots 0}$.
Em particular, a ação desta operação pode ser simulada pela transformação unitária $U$ que atua no estado de todos os zeros como

$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\ \\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{{j} \{sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.
\end{align} $$

## <a name="input"></a>Entrada

### <a name="coefficients--complexpolar"></a>coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O número de codificação do registo qubit está em formato pouco endiano. Espera-se que isto seja inicializado na base computacional do estado $\ket{0...0}$.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Coeficientes de entrada negativos $r_j < 0$ serão tratados como positivos com valor de $|r_j|$. `coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .

## <a name="references"></a>Referências

- Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.ApproximatePrepareArbitraryState](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)