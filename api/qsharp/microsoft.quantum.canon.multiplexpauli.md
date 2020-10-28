---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Operação MultiplexPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 0714e796c1e5ad097814bcf507f49f59a844e9ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715788"
---
# <a name="multiplexpauli-operation"></a>Operação MultiplexPauli

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma rotação Pauli condicionada a uma matriz de qubits.

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a>Descrição

Isto aplica uma operação unitária controlada por multiplique que executa rotações por ângulo $\theta_j$ sobre o operador pauli de um único qubit $P$ quando controlado pelo estado de número de $n$-qubit $\ket{j}$.
Em particular, a ação desta operação é representada pelo unitário

$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.
\end{align} $$

## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Matriz de até $2^n$ coeficientes $\theta_j$. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.


### <a name="pauli--pauli"></a>pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

O operador pauli $P$ que determina o eixo de rotação.


### <a name="control--littleendian"></a>controlo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Registo de qubit único que é rodado por $e^{i P \theta_j}$.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)