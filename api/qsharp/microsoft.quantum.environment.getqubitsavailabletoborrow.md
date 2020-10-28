---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operação GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712585"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Operação GetQubitsAvailableToBorrow

Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)

Pacote: [](https://nuget.org/packages/)


Devolve o número de qubits atualmente disponíveis para empréstimo.
Isto inclui qubits não-reutilizados; isto inclui os qubits devolvidos por `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits que poderiam ser atribuídos em `borrowing` comunicado.
Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Environment.GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)