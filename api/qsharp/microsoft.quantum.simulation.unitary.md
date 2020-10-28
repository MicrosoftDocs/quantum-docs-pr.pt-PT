---
uid: Microsoft.Quantum.Simulation.Unitary
title: Tipo definido pelo utilizador unitário
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725329"
---
# <a name="unitary-user-defined-type"></a>Tipo definido pelo utilizador unitário

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Representa a evolução sob um operador unitário.

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

