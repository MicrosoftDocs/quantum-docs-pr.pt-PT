---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: Função NearEqualityFactCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 95364541adfa1dc57b1f147c3992c9fd9f5f6c68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201568"
---
# <a name="nearequalityfactcp-function"></a>Função NearEqualityFactCP

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Afirma que um número complexo clássico tem o valor esperado até uma pequena tolerância de 1e-10.

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--complexpolar"></a>real : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

O número a ser verificado.


### <a name="expected--complexpolar"></a>esperado : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

O valor esperado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

