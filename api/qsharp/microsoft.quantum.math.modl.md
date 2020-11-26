---
uid: Microsoft.Quantum.Math.ModL
title: Função ModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227799"
---
# <a name="modl-function"></a>Função ModL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve o módulo de um número em relação a outro número.

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A entrada $a$ cujo módulo deve ser devolvido.


### <a name="b--bigint"></a>b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O número em relação ao qual o módulo de $a$ deve ser devolvido.



## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O módulo $a \bmod b$.