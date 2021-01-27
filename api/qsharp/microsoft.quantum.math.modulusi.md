---
uid: Microsoft.Quantum.Math.ModulusI
title: Função modulusi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847297"
---
# <a name="modulusi-function"></a>Função modulusi

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula o resíduo canónico do `value` `modulus` modulo.

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor : [Int](xref:microsoft.quantum.lang-ref.int)

O valor do qual o resíduo é calculado


### <a name="modulus--int"></a>módulo : [Int](xref:microsoft.quantum.lang-ref.int)

O módulo pelo qual os resíduos são tomadas, deve ser positivo



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Inteiro $r$ entre 0 e `modulus - 1` tal que `value - r` é divisível por módulo

## <a name="remarks"></a>Observações

Esta função comporta-se de forma diferente da forma como o operador `%` se comporta em C# e Q# pois, no resultado, é sempre um número inteiro não negativo entre 0 e , mesmo que o `modulus - 1` valor seja negativo.