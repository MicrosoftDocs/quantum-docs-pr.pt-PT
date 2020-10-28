---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operação DivideI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721222"
---
# <a name="dividei-operation"></a>Operação DivideI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Divide dois inteiros quânticos.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrição

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