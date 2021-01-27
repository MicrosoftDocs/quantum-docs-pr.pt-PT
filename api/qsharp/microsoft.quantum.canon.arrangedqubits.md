---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: Função De Bits Arranjados
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841082"
---
# <a name="arrangedqubits-function"></a>Função De Bits Arranjados

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Organize o controlo, o alvo e os qubits do ajudante de acordo com um índice

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Descrição

Devolve um conjunto qubit com o alvo no índice 0, e controla i no índice 2^i.  Os qubits do ajudante são inseridos em todas as outras posições da matriz.

## <a name="input"></a>Entrada

### <a name="controls--qubit"></a>controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>ajudante : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

