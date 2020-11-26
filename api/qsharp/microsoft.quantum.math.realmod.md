---
uid: Microsoft.Quantum.Math.RealMod
title: Função RealMod
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228258"
---
# <a name="realmod-function"></a>Função RealMod

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula o módulo entre dois números reais.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Entrada

### <a name="value--double"></a>valor : [Duplo](xref:microsoft.quantum.lang-ref.double)

Um número real $x dólares para tomar o módulo de.


### <a name="modulo--double"></a>modulo : [Duplo](xref:microsoft.quantum.lang-ref.double)

Um número real para tomar o módulo de $x$ em relação a.


### <a name="minvalue--double"></a>minValue : [Duplo](xref:microsoft.quantum.lang-ref.double)

O menor valor a ser devolvido por esta função.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observações

Esta função calcula o verdadeiro módulo envolvendo a linha real sobre o círculo unitário e, em seguida, encontrando o ângulo no círculo unitário correspondente à entrada.
`minValue`A entrada especifica então eficazmente onde cortar o círculo unitário.