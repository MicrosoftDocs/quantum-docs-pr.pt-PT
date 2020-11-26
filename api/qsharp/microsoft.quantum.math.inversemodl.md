---
uid: Microsoft.Quantum.Math.InverseModL
title: Função InverseModL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228190"
---
# <a name="inversemodl-function"></a>Função InverseModL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devoluções $b$ de modo que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O número invertido


### <a name="modulus--bigint"></a>módulo : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

O módulo segundo o qual os números são invertidos



## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Inteiro $b$ tal que $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.