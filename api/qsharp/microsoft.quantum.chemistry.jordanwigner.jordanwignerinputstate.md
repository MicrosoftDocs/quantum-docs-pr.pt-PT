---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Tipo definido pelo utilizador JordanWignerInputState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 81993a7449098c03639cf090fb36ed39c6ba17c0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214692"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>Tipo definido pelo utilizador JordanWignerInputState

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formato de dados passados de C# a Q# para representar a preparação do estado inicial O significado dos dados representados é determinado pelo algoritmo que os recebe.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

