---
uid: Microsoft.Quantum.Math.ModulusI
title: Função modulusi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227782"
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

Esta função comporta-se de forma diferente da forma como o operador `%` se comporta em C# e Q# pois, no resultado, é sempre um número inteiro positivo entre 0 e , mesmo que o `modulus - 1` valor seja negativo.