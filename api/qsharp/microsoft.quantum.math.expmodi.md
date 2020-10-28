---
uid: Microsoft.Quantum.Math.ExpModI
title: Função ExpModI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723366"
---
# <a name="expmodi-function"></a>Função ExpModI

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Devolve um inteiro elevado a um dado poder, no que diz respeito a um dado módulo.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Descrição

Vamos denotar expBase em $x$, poder de $p$ e modulus por $N$.
A função devolve $x^p \operatorname{mod} N$.

Assumimos que $N dólares, $x dólares são positivos e o poder não é negativo.

## <a name="input"></a>Entrada

### <a name="expbase--int"></a>expBase : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>módulo : [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Observações

Leva tempo proporcional ao número de bits `power` dentro , não o `power` próprio.