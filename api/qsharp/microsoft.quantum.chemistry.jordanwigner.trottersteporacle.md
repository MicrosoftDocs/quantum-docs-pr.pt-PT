---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: Função TrotterStepOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f7659616ea39d781137c26965cbf2005c5e634b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713772"
---
# <a name="trottersteporacle-function"></a>Função TrotterStepOracle

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


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



## <a name="output--intdoublequbit--unit-adj--ctl"></a>Saída : ([Int](xref:microsoft.quantum.lang-ref.int)[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))

Um tuple onde: `Int` é o número de qubits atribuídos, é , e a `Double` `1.0/trotterStepSize` operação é o passo Trotter.