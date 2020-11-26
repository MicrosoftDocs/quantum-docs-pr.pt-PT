---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: Função AllEqualityFactI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223889"
---
# <a name="allequalityfacti-function"></a>Função AllEqualityFactI

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Afirma que duas matrizes de valores inteiros são iguais.

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--int"></a>real : [Int](xref:microsoft.quantum.lang-ref.int)[]

A matriz que é produzida por um caso de teste de interesse.


### <a name="expected--int"></a>esperado : [Int](xref:microsoft.quantum.lang-ref.int)[]

A matriz que é esperada de um caso de teste de interesse.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser impressa se as matrizes não forem iguais.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

