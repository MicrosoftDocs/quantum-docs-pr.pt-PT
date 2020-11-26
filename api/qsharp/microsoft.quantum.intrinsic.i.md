---
uid: Microsoft.Quantum.Intrinsic.I
title: Eu operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 5aae7a5e3b5b441829de8f10f4df539ffc374954
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198950"
---
# <a name="i-operation"></a>Eu operação

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Executa a operação de identidade (no-op) num único qubit.

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Isto é um não-op. Está previsto para a completude e porque às vezes é útil chamar a identidade num algoritmo ou passá-la como parâmetro.