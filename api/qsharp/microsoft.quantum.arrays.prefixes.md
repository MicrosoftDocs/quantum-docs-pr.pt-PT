---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixa a função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845515"
---
# <a name="prefixes-function"></a>Prefixa a função

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma matriz, devolve todos os seus prefixos.

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>Descrição

Devolve uma matriz de todos os prefixos, começando com uma matriz que só tem o primeiro elemento até à matriz completa.

## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz : 'T[]

Uma variedade de elementos.



## <a name="output--t"></a>Saída : 'T[][]



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.

## <a name="example"></a>Exemplo

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```