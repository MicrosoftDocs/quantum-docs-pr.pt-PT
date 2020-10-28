---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido pelo utilizador de fração
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723660"
---
# <a name="fraction-user-defined-type"></a>Tipo definido pelo utilizador de fração

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Representa um número racional do `p/q` formulário. O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="numerator--int"></a>Numerador : [Int](xref:microsoft.quantum.lang-ref.int)

Numerador da fração.
### <a name="denominator--int"></a>Denominator : [Int](xref:microsoft.quantum.lang-ref.int)

Denominador da fração/