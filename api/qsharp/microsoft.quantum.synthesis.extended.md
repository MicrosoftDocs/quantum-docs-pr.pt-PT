---
uid: Microsoft.Quantum.Synthesis.Extended
title: Função estendida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855478"
---
# <a name="extended-function"></a>Função estendida

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Estende um espectro por coeficientes invertidos

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Entrada

### <a name="spectrum--int"></a>espectro : [Int](xref:microsoft.quantum.lang-ref.int)[]

Coeficientes espectrais



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

Coeficientes seguidos por cópia invertida

## <a name="example"></a>Exemplo

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```