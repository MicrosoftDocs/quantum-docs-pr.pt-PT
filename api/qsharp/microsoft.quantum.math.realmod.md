---
uid: Microsoft.Quantum.Math.RealMod
title: Função RealMod
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720406"
---
# <a name="realmod-function"></a>Função RealMod

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


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