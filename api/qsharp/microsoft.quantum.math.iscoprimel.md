---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: Função IsCoprimeL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722305"
---
# <a name="iscoprimel-function"></a>Função IsCoprimeL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Devoluções verdadeiras se $a$ e $b$ são co-prime e falso de outra forma.

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

o primeiro número de que a co-primalidade está a ser testada


### <a name="b--bigint"></a>b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

o segundo número de que co-primalidade está a ser testada



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

É verdade, se $a$ e $b$ são co-prime (por exemplo, o seu maior divisor comum é 1), e falso de outra forma