---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Obter Operação GetQubits DisponívelToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712582"
---
# <a name="getqubitsavailabletouse-operation"></a>Obter Operação GetQubits DisponívelToUse

Espaço de nome: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)

Pacote: [](https://nuget.org/packages/)


Devolve o número de qubits atualmente disponíveis para utilização.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits que poderiam ser atribuídos em `using` comunicado.
Se a máquina-alvo utilizada não fornecer estas informações, `-1` então é devolvida.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)