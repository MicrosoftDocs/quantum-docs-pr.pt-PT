---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Operação AproximadamenteMultiplexPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 8024df4608f14408bfcd46139e72454ff44b116f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207756"
---
# <a name="approximatelymultiplexpauli-operation"></a>Operação AproximadamenteMultiplexPauli

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma rotação Pauli condicionada a uma matriz de qubits, truncando pequenos ângulos de rotação de acordo com uma dada tolerância.

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Isto aplica uma operação unitária controlada por multiplique que executa rotações por ângulo $\theta_j$ sobre o operador pauli de um único qubit $P$ quando controlado pelo estado de número de $n$-qubit $\ket{j}$.
Em particular, a ação desta operação é representada pelo unitário

$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.
\end{align}

##

## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma tolerância abaixo da qual pequenos coeficientes são truncados.


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

- [Microsoft.Quantum.Canon.MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)