---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: AplicarToach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717594"
---
# <a name="applytoeach-operation"></a>AplicarToach

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação de um único qubit a cada elemento num registo.

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--t--unit"></a>singleElementOperação : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Operação a aplicar a cada qubit.


### <a name="register--t"></a>registo : 'T[]

Matriz de qubits para aplicar a operação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo no qual a operação atua.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToEachC](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft.quantum.canon.applyToEacha](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft.Quantum.Canon.ApplyToEachCA](xref:Microsoft.Quantum.Canon.ApplyToEachCA)