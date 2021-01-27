---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: Função qubitizaçãoOo
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: cf6fe04b3f629c4ca4a7c27d8519a4cb42d07630
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835843"
---
# <a name="qubitizationoracle-function"></a>Função qubitizaçãoOo

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Devolve a operação de qubitização e os parâmetros necessários para executá-la.

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Entrada

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian descrito por `JordanWignerEncodingData` formato.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Saída : ([Int (Duplo,](xref:microsoft.quantum.lang-ref.int)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl))[](xref:microsoft.quantum.lang-ref.double)

Um tuple onde: `Int` é o número de qubits atribuídos, é a única norma dos `Double` coeficientes hamiltonianos, e a operação é a caminhada quântica criada pela Qubitização.