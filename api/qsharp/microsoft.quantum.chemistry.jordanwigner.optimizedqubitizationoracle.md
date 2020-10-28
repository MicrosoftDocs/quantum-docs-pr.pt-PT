---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle
title: OtimizadoQubitizaçãoAçãososação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedQubitizationOracle
qsharp.summary: Returns T-count optimized Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: c67dc5890fe1444c1689eb803ed3d24b2dbe5ce2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713887"
---
# <a name="optimizedqubitizationoracle-function"></a>OtimizadoQubitizaçãoAçãososação

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Devolve a contagem de T operações de qubitização otimizada e os parâmetros necessários para executá-la.

```qsharp
function OptimizedQubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, targetError : Double) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Entrada

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian descrito por `JordanWignerEncodingData` formato.


### <a name="targeterror--double"></a>targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)

Erro de preparação do estado auxillary.



## <a name="output--intdoublequbit--unit-adj--ctl"></a>Saída : ([Int](xref:microsoft.quantum.lang-ref.int)[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))

Um tuple onde: `Int` é o número de qubits atribuídos, é a única norma dos `Double` coeficientes hamiltonianos, e a operação é a caminhada quântica criada pela Qubitização.