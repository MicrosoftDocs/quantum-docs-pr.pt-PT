---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operação PrepareIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855879"
---
# <a name="prepareidentity-operation"></a>Operação PrepareIdentity

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um registo, prepara-se o registo no estado máximo misto.

O registo é preparado no estado $\boldone / 2^N$ aplicando o canal de despolarizante completo em cada qubit, onde $N$ é o comprimento do registo.

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo cujo estado deve ser despolarizado da forma acima descrita.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.preparation.preparesingleQubitIdentity](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)