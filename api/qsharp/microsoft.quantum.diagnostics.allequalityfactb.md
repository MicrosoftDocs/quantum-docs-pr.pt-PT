---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: Função AllEqualityFactB
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713075"
---
# <a name="allequalityfactb-function"></a>Função AllEqualityFactB

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Afirma que duas matrizes de valores booleanos são iguais.

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--bool"></a>real : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

A matriz que é produzida por um caso de teste de interesse.


### <a name="expected--bool"></a>esperado : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

A matriz que é esperada de um caso de teste de interesse.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser impressa se as matrizes não forem iguais.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

