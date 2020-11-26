---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operação GetQubitsAvailableToBorrow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201466"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operação GetQubitsAvailableToBorrow

Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve o número de qubits atualmente disponíveis para empréstimo.

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits que podem ser emprestados e não serão atribuídos como parte de uma `borrowing` declaração.
Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Environment.GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)