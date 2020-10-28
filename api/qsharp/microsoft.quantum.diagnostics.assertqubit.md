---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AfirmaQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712946"
---
# <a name="assertqubit-operation"></a>AfirmaQubit

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Afirma que o qubit `q` está no estado esperado do operador Pauli Z.

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="expected--__invalidresult__"></a>esperado : __inválido <Result>__

Em que estado se espera que o qubit esteja: `Zero` ou `One` .


### <a name="q--qubit"></a>q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit cujo estado é afirmado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permite afirmar estados de qubit arbit arbit em vez de apenas $Z dólares.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)