---
uid: Microsoft.Quantum.Math.RealMod
title: Função RealMod
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848354"
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



## <a name="example"></a>Exemplo

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Observações

Esta função calcula o verdadeiro módulo envolvendo a linha real sobre o círculo unitário e, em seguida, encontrando o ângulo no círculo unitário correspondente à entrada.
`minValue`A entrada especifica então eficazmente onde cortar o círculo unitário.