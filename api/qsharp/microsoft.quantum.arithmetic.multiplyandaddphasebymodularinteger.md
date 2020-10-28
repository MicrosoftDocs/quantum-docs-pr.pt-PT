---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operação MultiplyAndAddPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719806"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>Operação MultiplyAndAddPhaseByModularInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


O mesmo que MultiplyAndAddByModularInteger, mas assume que os sumários e codificam inteiros em QFT.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="constmultiplier--int"></a>constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)

Um inteiro $a$ a ser adicionado a cada rótulo de estado base.


### <a name="modulus--int"></a>módulo : [Int](xref:microsoft.quantum.lang-ref.int)

O módulo $N$ que adição e multiplicação é tomada no que diz respeito.


### <a name="multiplier--littleendian"></a>multiplicador : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Um registo quântico que represente um número inteiro não assinado cujo valor deve ser adicionado a cada rótulo de estado de base de `summand` .


### <a name="phasesummand--phaselittleendian"></a>faseSumand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Um registo quântico que representa um número inteiro não assinado para usar como alvo para esta operação.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Assume que `phaseSummand` tem a parte mais alta definida para 0.
Também assume que o valor `phaseSummand` é inferior a $N$.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Aithmetic.MultiplyAndAddByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)