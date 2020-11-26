---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operação MeasureInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222648"
---
# <a name="measureinteger-operation"></a>Operação MeasureInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mede o conteúdo de um registo quântico e converte-o num inteiro. A medição é efetuada no que diz respeito à base computacional padrão, ou seja, a eigenbasis de `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Entrada

### <a name="target--littleendian"></a>alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Um registo quântico na codificação de pequenas extremidades.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro não assinado que contém o valor medido de `target` .

## <a name="remarks"></a>Observações

Esta operação reinicia o seu registo de entrada no estado $\ket{00\cdots 0}$ adequado para o lançamento de volta para uma máquina-alvo.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)