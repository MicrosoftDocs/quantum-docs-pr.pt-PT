---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843430"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Afirma que o qubit mais significativo de um registo qubit que representa um número inteiro não assinado está num determinado estado.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="value--__invalidresult__"></a>valor : __inválido <Result>__

O valor da parte mais alta a ser afirmado.


### <a name="number--littleendian"></a>número : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Inteiro não assinado, do qual a parte mais alta é verificada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A versão controlada desta operação ignora os controlos.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Intrínseco.Assert](xref:Microsoft.Quantum.Intrinsic.Assert)