---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operação MultiplyAndAddByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 169326879919b5b72d600c33d624776b720cc6bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222597"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>Operação MultiplyAndAddByModularInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa uma multiplicação modular multiplicadora e adiciona por constantes de número inteiro num registo qubit.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Implementa o mapa $$ \start{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{x} \ket{x} \ket{$y $a $N x

## <a name="input"></a>Entrada

### <a name="constmultiplier--int"></a>constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro $a$ a ser adicionado a cada rótulo de estado base.


### <a name="modulus--int"></a>módulo : [Int](xref:microsoft.quantum.lang-ref.int)

O módulo $N$ que adição e multiplicação é tomada no que diz respeito.


### <a name="multiplier--littleendian"></a>multiplicador : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Um registo quântico que represente um número inteiro não assinado cujo valor deve ser adicionado a cada rótulo de estado de base de `summand` .


### <a name="summand--littleendian"></a>summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Um registo quântico que representa um número inteiro não assinado para usar como alvo para esta operação.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

- Para o diagrama do circuito e explicação consulte a figura 6 na [página 7 do arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Esta operação corresponde à CMULT(a)MOD(N) em [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Aithmetic.MultiplyAndAddPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)