---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Tipo definido pelo utilizador HTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714867"
---
# <a name="hterm-user-defined-type"></a>Tipo definido pelo utilizador HTerm

Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacote: [](https://nuget.org/packages/)


Formato de dados passados de C# a Q# para representar um termo do Hamiltonian.
O significado dos dados representados é determinado pelo algoritmo que os recebe.

```qsharp

newtype HTerm = (Int[], Double[]);
```

