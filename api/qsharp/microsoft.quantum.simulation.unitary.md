---
uid: Microsoft.Quantum.Simulation.Unitary
title: Tipo definido pelo utilizador unitário
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: f148b59d2445f964fc0332e2010571a0ace2d4ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858403"
---
# <a name="unitary-user-defined-type"></a>Tipo definido pelo utilizador unitário

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa a evolução sob um operador unitário.

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

