---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829790"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>AssertQubitIsInStateWithinTolerance

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Afirma que um qubit no estado esperado.

`expected` representa um vetor complexo, $\ket{\psi} = \start{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}}$.
O primeiro elemento dos tuples que representam cada um dos $a$, $b$ é a parte real do número complexo, enquanto o segundo é a parte imaginária.
O último argumento define a tolerância com que a afirmação é feita.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Entrada

### <a name="expected--complexcomplex"></a>esperado:[(Complexo,](xref:Microsoft.Quantum.Math.Complex)[Complexo)](xref:Microsoft.Quantum.Math.Complex)

Amplitudes complexas esperadas para $\ket {0} $ e $\ket {1} $, respectivamente.


### <a name="register--qubit"></a>registo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cujo estado deve ser afirmado. Note que este qubit é assumido como separável de outros qubits atribuídos, e não emaranhado.


### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

Tolerância adídria pela qual as amplitudes reais são permitidas a desviar-se do esperado.
Consulte as observações abaixo para mais detalhes.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemplo

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>Observações

O seguinte código Mathematica pode ser usado para verificar expressões para mi, mx, my, mz:

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

A tolerância é a distância $L \_ {\infty}$ entre vetor real 3 dimensional (x2,x₃,x₄) definido por $\langle\psi|\psi\rangle = x \_ 1 I + x \_ 2 X \_ 3 Y + x \_ 04 Z$ e vetor real (y2,y₃,y₄) definidos por ρ = y₁I + y2X + y₃Y + y₄Z onde ρ é a matriz de densidade correspondente ao estado do registo.
Isto só é verdade sob o pressuposto de que Tr(ρ) e Tr(|ψ⟩⟨ψ|) são ambos 1 (por exemplo, x₁ = 1/2, y₁ = 1/2).
Se não for esse o caso, a função afirma que l∞ distância entre (x2-x₁,x₃-x₁,x₄-x₁,x₄+x₁) e (y2-y₁,y₃-y₁₄-y₁,y₄+y₁) é inferior ao parâmetro de tolerância.