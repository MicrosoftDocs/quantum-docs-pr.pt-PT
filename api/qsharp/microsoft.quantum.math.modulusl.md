---
uid: Microsoft.Quantum.Math.ModulusL
title: Função de módulol
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194938"
---
# <a name="modulusl-function"></a>Função de módulol

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula o resíduo canónico do `value` `modulus` modulo.

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Entrada

### <a name="value--bigint"></a>valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O valor do qual o resíduo é calculado


### <a name="modulus--bigint"></a>módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O módulo pelo qual os resíduos são tomadas, deve ser positivo



## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Inteiro $r$ entre 0 e `modulus - 1` tal que `value - r` é divisível por módulo

## <a name="remarks"></a>Observações

Esta função comporta-se de forma diferente da forma como o operador `%` se comporta em C# e Q# pois, no resultado, é sempre um número inteiro positivo entre 0 e , mesmo que o `modulus - 1` valor seja negativo.