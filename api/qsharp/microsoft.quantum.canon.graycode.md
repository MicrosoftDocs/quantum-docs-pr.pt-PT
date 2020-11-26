---
uid: Microsoft.Quantum.Canon.GrayCode
title: Função GrayCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206889"
---
# <a name="graycode-function"></a>Função GrayCode

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cria sequências de código cinza

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Entrada

### <a name="n--int"></a>n : [Int](xref:microsoft.quantum.lang-ref.int)

Número de bits



## <a name="output--intint"></a>Saída :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]

Conjunto de tuples. Primeiro valor em tuple é valor na sequência GrayCode Segundo valor em tuple é posição para alterar o valor atual para obter o próximo.