---
uid: Microsoft.Quantum.Canon.GrayCode
title: Função GrayCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840503"
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

## <a name="example"></a>Exemplo

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```