---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Função TamanhosajustedTruthTable
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202928"
---
# <a name="sizeadjustedtruthtable-function"></a>Função TamanhosajustedTruthTable

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ajusta a tabela da verdade a partir de matriz de Booleans de acordo com o número de variáveis

Uma nova matriz é devolvida de `2^numVars` comprimento, possivelmente exigindo estender `table` o tamanho com entradas ou `false` truncar-lo a `2^numVars` elementos.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="table--bool"></a>tabela : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabela da verdade como conjunto de valores da verdade


### <a name="numvars--int"></a>numVars : [Int](xref:microsoft.quantum.lang-ref.int)

Número de variáveis



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabela de verdade ajustada de tamanho