---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Preparar Operação Do Estado-ParparseMultiConfigurational
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713845"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a>Preparar Operação Do Estado-ParparseMultiConfigurational

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Preparação estatal multi-configuracional escassa do estado experimental adicionando excitações ao estado experimental inicial.

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="initialstatepreparation--qubit--unit"></a>prescrição inicial: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Unitário para preparar o estado inicial do julgamento.


### <a name="excitations--jordanwignerinputstate"></a>excitações : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]

Excitações do estado experimental inicial representadas pela amplitude da excitação e os índices qubit sobre os atos de excitação.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de Hamiltonian.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

