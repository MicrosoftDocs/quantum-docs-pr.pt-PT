---
uid: Microsoft.Quantum.Math.InverseModL
title: Função InverseModL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723632"
---
# <a name="inversemodl-function"></a>Função InverseModL

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


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