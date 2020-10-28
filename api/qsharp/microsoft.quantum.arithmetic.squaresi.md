---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operação SquareSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719531"
---
# <a name="squaresi-operation"></a>Operação SquareSI

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


A Praça assinou o inteiro `xs` e armazena o resultado em , que deve ser zero `result` inicialmente.

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="xs--signedlittleendian"></a>xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n-bit inteiro para quadrado (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>resultado : [AssinadoLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Resultado de 2n-bit (SignedLittleEndian), deve estar no estado $\ket {0} $ inicialmente.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A implementação baseia-se na IntegerSquare.