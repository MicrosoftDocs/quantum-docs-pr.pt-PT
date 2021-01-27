---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Operação EstimativaTermExpectation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835675"
---
# <a name="estimatetermexpectation-operation"></a>Operação EstimativaTermExpectation

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Calcula a energia associada a um dado termo Jordan-Wigner Hamiltonian

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Descrição

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