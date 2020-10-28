---
uid: Microsoft.Quantum.Math.ExpModL
title: Função ExpModL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723730"
---
# <a name="expmodl-function"></a>Função ExpModL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Devolve um inteiro elevado a um dado poder, no que diz respeito a um dado módulo.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Descrição

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