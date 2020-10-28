---
uid: Microsoft.Quantum.Intrinsic.T
title: Operação T
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720851"
---
# <a name="t-operation"></a>Operação T

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [](https://nuget.org/packages/)


Aplica o portão T a um único qubit.

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a>Descrição

Esta operação pode ser simulada pela matriz unitária \start{align} T \mathrel{:=} \start{bmatrix} 1 & \\ \\ 0 0 & e^{i \pi / 4} \end{bmatrix}.
\end{align}

## <a name="input"></a>Entrada

### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ao qual o portão deve ser aplicado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

