---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: Função NearEqualityFactD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712652"
---
# <a name="nearequalityfactd-function"></a>Função NearEqualityFactD

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Afirma que um valor clássico do ponto flutuante tem o valor esperado até uma pequena tolerância de 1e-10.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--double"></a>real : [Duplo](xref:microsoft.quantum.lang-ref.double)

O número a ser verificado.


### <a name="expected--double"></a>esperado : [Duplo](xref:microsoft.quantum.lang-ref.double)

O valor esperado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Isto equivale a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> uma tolerância codificada de $10^ {-10} $.