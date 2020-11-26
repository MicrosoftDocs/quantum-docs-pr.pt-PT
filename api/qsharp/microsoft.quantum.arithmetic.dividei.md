---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operação DivideI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223311"
---
# <a name="dividei-operation"></a>Operação DivideI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Divide dois inteiros quânticos.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

`xs` irá segurar o restante `xs - floor(xs/ys) * ys` e `result` irá aguentar `floor(xs/ys)` .

## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n dividendo de $-bit, será substituído pelo restante.


### <a name="ys--littleendian"></a>ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

divisor de $n de dólares


### <a name="result--littleendian"></a>resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n resultado de $-bit, deve estar no estado $\ket {0} $ inicialmente e será substituído pelo resultado da divisão inteiro.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Usa uma abordagem padrão de mudança e subtraição para implementar a divisão.
A versão controlada é especializada de modo a que a subtração não exija controlos adicionais.