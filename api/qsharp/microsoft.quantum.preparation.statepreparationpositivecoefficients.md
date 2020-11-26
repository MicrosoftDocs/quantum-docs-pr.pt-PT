---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: Função de EstadoPreparaçõesPositiveCoefficients
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193255"
---
# <a name="statepreparationpositivecoefficients-function"></a>Função de EstadoPreparaçõesPositiveCoefficients

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Os EstadosPreparationPositiveCoefficients foram depreciados. Por favor, use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> em vez disso.

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



## <a name="output--littleendian--unit--is-adj--ctl"></a>Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl

Uma operação unitária de preparação do estado $U$.

## <a name="remarks"></a>Observações

Coeficientes de entrada negativos $\alpha_j < 0$ serão tratados como se positivo com valor $\alpha_j.$. `coefficients` serão acolchoados com elementos $\alpha_j = 0,0$ se forem especificados menos de $2^n$