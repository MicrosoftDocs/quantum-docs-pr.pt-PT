---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: Função ReversedOpBEA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719698"
---
# <a name="reversedopbea-function"></a>Função ReversedOpBEA

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Dada uma operação que requer uma entrada de grande ponta, devolve uma nova operação que requer uma entrada pouco endiana.

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="op--bigendian--unit-adj"></a>op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj

A operação cuja entrada deve ser invertida.



## <a name="output--littleendian--unit-adj"></a>Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj

Uma nova operação que aceita a sua entrada como um registo de pequenas finais.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Aithmetic.ApplyReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [Microsoft.Quantum.Aithmetic.ReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [Microsoft.Quantum.Aithmetic.ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft.Quantum.Aithmetic.ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)