---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Preparar OperaçãoChoiStateCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709446"
---
# <a name="preparechoistateca-operation"></a>Preparar OperaçãoChoiStateCA

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Prepara o estado Choi-Jamiłkowski para uma determinada operação com variantes controladas e adjacentes em registos de referência e alvo.

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit-adj--ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl




### <a name="reference--qubit"></a>referência: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.PrepareChoiState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)