---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operação EstimativaTermExpectation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224654"
---
# <a name="estimatetermexpectation-operation"></a>Operação EstimativaTermExpectation

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Calcula a energia associada a um dado termo Jordan-Wigner Hamiltonian

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Description

Esta operação estima o valor de expectativa associado a cada operador de medição e multiplica-o pelo coeficiente correspondente, utilizando a amostragem.
Os resultados são agregados numa variável que contém a energia do termo Jordan-Wigner.

## <a name="input"></a>Entrada

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj

O unitário usado para a preparação do estado.


### <a name="ops--pauli"></a>ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]

Os operadores de medição do termo Jordan-Wigner.


### <a name="coeffs--double"></a>coeffs : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Os coeficientes do termo Jordan-Wigner.


### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits necessários para simular o sistema molecular.


### <a name="nsamples--int"></a>nSamples : [Int](xref:microsoft.quantum.lang-ref.int)

O número de amostras a utilizar para a estimativa do termo expectativa.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

A energia associada ao termo Jordan-Wigner.