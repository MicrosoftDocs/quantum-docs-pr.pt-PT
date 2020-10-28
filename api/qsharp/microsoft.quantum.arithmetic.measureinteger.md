---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operação MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720970"
---
# <a name="measureinteger-operation"></a>Operação MeasureInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


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