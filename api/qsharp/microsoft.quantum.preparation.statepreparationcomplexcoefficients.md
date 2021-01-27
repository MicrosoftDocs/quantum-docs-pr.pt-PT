---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: Função de Prescrição DePreparaçõesComplexCoficientes
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: c16df0fe075b15cff745a6b7d5b79aac39c14d09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856140"
---
# <a name="statepreparationcomplexcoefficients-function"></a>Função de Prescrição DePreparaçõesComplexCoficientes

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients foi depreciado. Por favor, use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> em vez disso.

Devolve uma operação que prepara um estado quântico específico.

A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0...0}$...$$.$-qubit base de base computacional estado $\ket{0...$$...

A ação de U num registo recém-atribuído é dada por $$ \start{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^2^2^0^2^0^2^0^2^0^2^0 n-1}r_j e^{i t_j}\ket{j}}{|r_j| sum_{{}2}}
\end{align} $$

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="coefficients--complexpolar"></a>coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.



## <a name="output--littleendian--unit--is-adj--ctl"></a>Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl

Uma operação unitária de preparação do estado $U$.

## <a name="example"></a>Exemplo

O seguinte corte prepara o estado quântico $\ket{\psi}=e^{i 0.1}\sqrt{1/8}\ket {0} +\sqrt{7/8}\ket {2} $ in the qubit register `qubitsLE` .

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let phases = [0.1, 0.0, 0.0, 0.0];
mutable complexNumbers = new ComplexPolar[4];
for (idx in 0..3) {
    set complexNumbers[idx] = ComplexPolar(amplitudes[idx], phases[idx]);
}
let op = StatePreparationComplexCoefficients(complexNumbers);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a>Observações

Coeficientes de entrada negativos $r_j < 0$ serão tratados como positivos com valor de $|r_j|$. `coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .