---
uid: Microsoft.Quantum.Math.BigFraction
title: Tipo definido pelo utilizador bigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723212"
---
# <a name="bigfraction-user-defined-type"></a>Tipo definido pelo utilizador bigFraction

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Representa um número racional do `p/q` formulário. O inteiro `p` é o primeiro elemento da tuple e é o segundo elemento da `q` tuple.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Itens nomeados

### <a name="numerator--bigint"></a>Numerador : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Numerador da fração.
### <a name="denominator--bigint"></a>Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Denominador da fração/