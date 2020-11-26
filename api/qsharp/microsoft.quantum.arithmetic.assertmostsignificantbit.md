---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223787"
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