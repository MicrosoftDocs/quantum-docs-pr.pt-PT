---
uid: Microsoft.Quantum.Canon.Fst
title: Função Fst
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206940"
---
# <a name="fst-function"></a>Função Fst

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um par, devolve o seu primeiro elemento.

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>Entrada

### <a name="pair--tu"></a>par : ('T,'U)

Uma tuple com dois elementos.



## <a name="output--t"></a>Saída : 'T

O primeiro elemento `pair` de.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo do primeiro membro do par.
### <a name="u"></a>'U

O tipo do segundo membro do par.