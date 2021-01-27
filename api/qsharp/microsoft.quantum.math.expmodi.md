---
uid: Microsoft.Quantum.Math.ExpModI
title: Função ExpModI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857040"
---
# <a name="expmodi-function"></a>Função ExpModI

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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