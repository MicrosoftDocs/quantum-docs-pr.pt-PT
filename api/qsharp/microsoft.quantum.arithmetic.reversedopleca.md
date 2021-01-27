---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: Função ReversedOpLECA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: d4245437f2b71abb8bf1bbe4db43ae7d2ee23799
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845741"
---
# <a name="reversedopleca-function"></a>Função ReversedOpLECA

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma operação que requer uma entrada pouco endiana, devolve uma nova operação que requer uma grande entrada de luxo.

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--littleendian--unit--is-adj--ctl"></a>op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl

A operação cuja entrada deve ser invertida.



## <a name="output--bigendian--unit--is-adj--ctl"></a>Saída : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl

Uma nova operação que aceita a sua entrada como um registo de grandes pontas.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Aithmetic.ApplyReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [Microsoft.Quantum.Aithmetic.ReversedOpLE](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft.Quantum.Aithmetic.ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft.Quantum.Aithmetic.ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)