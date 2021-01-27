---
uid: Microsoft.Quantum.Math.Fraction
title: Tipo definido pelo utilizador de fração
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857505"
---
# <a name="fraction-user-defined-type"></a>Tipo definido pelo utilizador de fração

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um número racional do `p/q` formulário. O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="numerator--int"></a>Numerador : [Int](xref:microsoft.quantum.lang-ref.int)

Numerador da fração.
### <a name="denominator--int"></a>Denominator : [Int](xref:microsoft.quantum.lang-ref.int)

Denominador da fração/