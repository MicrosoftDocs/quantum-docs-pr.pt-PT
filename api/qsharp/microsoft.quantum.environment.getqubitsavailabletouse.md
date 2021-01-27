---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Obter Operação GetQubits DisponívelToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827807"
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