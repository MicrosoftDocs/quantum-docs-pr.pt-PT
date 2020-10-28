---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: Função de Prescrição DePreparaçõesComplexCoficientes
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722907"
---
# <a name="statepreparationcomplexcoefficients-function"></a>Função de Prescrição DePreparaçõesComplexCoficientes

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Devolve uma operação que prepara um estado quântico específico.

A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes complexos $r_j e^{i t_j}$ do estado de base computacional $n$-qubit $\ket{0...0}$...$.$.$.$.$.$$.$$$$$$$$$-qubit base de base computacional estado $\ket{0...$$....$.$...

A ação de U num registo recém-atribuído é dada por $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{{{r_j sum_{{{{2}}.
\end{align} $$

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="coefficients--complexpolar"></a>coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matriz de até $2^n$ coeficientes complexos representados pelo seu valor absoluto e fase $(r_j, t_j)$. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.



## <a name="output--littleendian--unit-adj--ctl"></a>Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Uma operação unitária de preparação do estado $U$.

## <a name="remarks"></a>Observações

Coeficientes de entrada negativos $r_j < 0$ serão tratados como se positivos com valor $/ r_j `coefficients` serão acolchoados com elementos $(r_j, t_j) = (0,0, 0,0)$ se forem especificados menos de $2^n$ .