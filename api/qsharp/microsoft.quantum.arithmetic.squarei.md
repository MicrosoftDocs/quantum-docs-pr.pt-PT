---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operação SquareI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719542"
---
# <a name="squarei-operation"></a>Operação SquareI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Calcula o quadrado do inteiro `xs` em , que deve ser zero `result` inicialmente.

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n número de $-bit para quadrado (LittleEndian)


### <a name="result--littleendian"></a>resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Resultado de $2n$-bit (LittleEndian), deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Usa uma abordagem padrão de mudança e adição para calcular o quadrado. Poupa $n-1$ qubits em comparação com a solução straight-forward que primeiro copia xs antes de aplicar um multiplicador regular e, em seguida, desfazer a operação de cópia.