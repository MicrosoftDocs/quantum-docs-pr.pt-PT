---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Operação AssertPhase
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712949"
---
# <a name="assertphase-operation"></a>Operação AssertPhase

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Afirma que a fase de um estado de superposição igual tem o valor esperado.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Descrição

Esta operação afirma que a fase $\phi$ de um estado quântico que pode ser expressa como $\frac{e^{i t}}}}sqrt {2} }(e^{i\phi}ket {0} + e^-i\phi}\ket {1} )$ para algum real arbitrário $t$ tem o valor esperado.

## <a name="input"></a>Entrada

### <a name="expected--double"></a>esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)

O valor esperado de $\phi \in (\pi,\pi]$.


### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit que armazena o estado esperado.


### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

Tolerância absoluta na diferença entre real e esperado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

