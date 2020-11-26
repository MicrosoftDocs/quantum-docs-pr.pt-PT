---
uid: Microsoft.Quantum.Math.ExpModL
title: Função ExpModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210755"
---
# <a name="expmodl-function"></a>Função ExpModL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve um inteiro elevado a um dado poder, no que diz respeito a um dado módulo.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Description

Vamos denotar expBase em $x$, poder de $p$ e modulus por $N$.
A função devolve $x^p \operatorname{mod} N$.

Assumimos que $N dólares, $x dólares são positivos e o poder não é negativo.

## <a name="input"></a>Entrada

### <a name="expbase--bigint"></a>expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>poder : [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Observações

Leva tempo proporcional ao número de bits `power` dentro , não o `power` próprio.