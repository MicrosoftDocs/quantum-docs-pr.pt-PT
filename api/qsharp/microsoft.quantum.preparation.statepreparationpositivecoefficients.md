---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Função de EstadoPreparaçõesPositiveCoefficients
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722893"
---
# <a name="statepreparationpositivecoefficients-function"></a>Função de EstadoPreparaçõesPositiveCoefficients

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Devolve uma operação que prepara o estado quântico.

A operação devolvida $U$ prepara um estado quântico arbitrário $\ket{\psi}$ com coeficientes positivos $\alpha_j\ge 0$ do estado de base computacional $n$-qubit $\ket{0...0}$..$.$.$.$$$$$-00}$.$$$$-qubit basis basis state $\ket{0...$$.$.$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$.$$$$$$$$$$$$$$$$$$$00}$.$$$$$$$-qubit basis basis state $\ket{0...0}$.

A ação de U num registo recém-atribuído é dada por $$ \start{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^^^{2^n-1}\alpha_j \ket{j}}{{\sqrt{\sum_{j=0}^{2^n-1}[\alpha_j^2}}}
\end{align} $$

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Matriz de até $2^n$ coeficientes $\alpha_j$. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.



## <a name="output--littleendian--unit-adj--ctl"></a>Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Uma operação unitária de preparação do estado $U$.

## <a name="remarks"></a>Observações

Coeficientes de entrada negativos $\alpha_j < 0$ serão tratados como se positivo com valor $\alpha_j.$. `coefficients` serão acolchoados com elementos $\alpha_j = 0,0$ se forem especificados menos de $2^n$