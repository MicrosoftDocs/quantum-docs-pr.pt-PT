---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: Função TrotterStepOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: be3354a60bab6b065b42df7db9ae8ff3340be8e7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214471"
---
# <a name="trottersteporacle-function"></a>Função TrotterStepOracle

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Devolve a operação do passo Trotter e os parâmetros necessários para executá-lo.

```qsharp
function TrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Entrada

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian descrito por `JordanWignerEncodingData` formato.


### <a name="trotterstepsize--double"></a>trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)

Tamanho do passo do integrador Trotter.


### <a name="trotterorder--int"></a>trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)

Ordem do integrador Trotter.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Saída : ([Int (Duplo,](xref:microsoft.quantum.lang-ref.int)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl))[Double](xref:microsoft.quantum.lang-ref.double)

Um tuple onde: `Int` é o número de qubits atribuídos, é , e a `Double` `1.0/trotterStepSize` operação é o passo Trotter.