---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Obter Operação GetQubits DisponívelToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201415"
---
# <a name="getqubitsavailabletouse-operation"></a>Obter Operação GetQubits DisponívelToUse

Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve o número de qubits atualmente disponíveis para utilização.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits que poderiam ser atribuídos em `using` comunicado.
Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)