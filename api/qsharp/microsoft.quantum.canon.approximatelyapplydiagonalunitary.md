---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: Operação aproximadamenteApplyDiagonalUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 5d8f6646c124f4296b9cd2abd71e73de5a530e55
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850338"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a>Operação aproximadamenteApplyDiagonalUnitary

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica um conjunto de fases complexas aos estados de base numérica de um registo de qubits, truncando pequenos ângulos de rotação de acordo com uma dada tolerância.

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação implementa uma diagonal unitária que aplica uma fase complexa $e^{i \theta_j}$ no estado do número de $n$-qubit $\ket{j}$.
Em particular, esta operação pode ser representada pelo unitário

$$ \begin{align} U = \sum^{2^n-1}_{j=0}i\i\theta_j}\ket{j}bra{j}}
\end{align} $$

## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma tolerância abaixo da qual pequenos coeficientes são truncados.


### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Matriz de até $2^n$ coeficientes $\theta_j$. O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .

## <a name="references"></a>Referências

- Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyDiagonalunitary](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)