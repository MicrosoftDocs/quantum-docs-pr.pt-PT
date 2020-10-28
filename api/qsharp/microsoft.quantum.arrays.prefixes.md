---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixa a função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718942"
---
# <a name="prefixes-function"></a>Prefixa a função

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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