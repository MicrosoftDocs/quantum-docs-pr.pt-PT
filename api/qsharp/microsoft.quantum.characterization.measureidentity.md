---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operação MeasureIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851816"
---
# <a name="measureidentity-operation"></a>Operação MeasureIdentity

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mede o operador de identidade num registo de qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Entrada

### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

O registo a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O valor do resultado `Zero` .

## <a name="remarks"></a>Observações

Uma vez que $\boldone$ tem apenas o valor de $1$, e não tem um valor de eigen negativo, esta operação volta sempre `Zero` , correspondente ao eigenvalue $+1 = (-1)^0$, e não causa um colapso do estado de `register` .

Por si só, esta operação não é útil, mas é útil no contexto da tomografia do processo, uma vez que fornece informações sobre a preservação de vestígios de um processo quântico.
Em particular, uma máquina-alvo com medição de perda deve substituir esta operação por uma medição real de $\boldone$.