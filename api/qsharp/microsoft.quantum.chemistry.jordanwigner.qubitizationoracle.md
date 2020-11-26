---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: Função qubitizaçãoOo
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: d67cf10b7516c638df6f5d13cd548bf6696443fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214454"
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



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Saída : ([Int (Duplo,](xref:microsoft.quantum.lang-ref.int)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl))[Double](xref:microsoft.quantum.lang-ref.double)

Um tuple onde: `Int` é o número de qubits atribuídos, é a única norma dos `Double` coeficientes hamiltonianos, e a operação é a caminhada quântica criada pela Qubitização.