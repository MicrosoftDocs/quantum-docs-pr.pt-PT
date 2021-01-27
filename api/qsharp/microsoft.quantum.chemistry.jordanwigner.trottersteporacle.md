---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: Função TrotterStepOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: a3164da1ce9ae1f72ec2fb1fa151159768cd5a4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835805"
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



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Saída : ([Int (Duplo,](xref:microsoft.quantum.lang-ref.int)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl))[](xref:microsoft.quantum.lang-ref.double)

Um tuple onde: `Int` é o número de qubits atribuídos, é , e a `Double` `1.0/trotterStepSize` operação é o passo Trotter.