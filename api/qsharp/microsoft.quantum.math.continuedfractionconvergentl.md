---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: Continuação da FunçãoFractionConvergentL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 14f0eee5565b3e80f4090a2d3763ef96c928368d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856396"
---
# <a name="continuedfractionconvergentl-function"></a>Continuação da FunçãoFractionConvergentL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Encontra a fração contínua convergente mais próxima `fraction` de com o denominador menos ou igual a `denominatorBound`

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a>Entrada

### <a name="fraction--bigfraction"></a>fração : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)




### <a name="denominatorbound--bigint"></a>denominadorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigfraction"></a>Saída : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)

Fração continuada mais próxima `fraction` de com o denominador menos ou igual a `denominatorBound`