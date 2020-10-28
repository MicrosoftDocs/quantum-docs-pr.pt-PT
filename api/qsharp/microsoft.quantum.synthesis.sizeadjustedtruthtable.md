---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Função TamanhosajustedTruthTable
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725469"
---
# <a name="sizeadjustedtruthtable-function"></a>Função TamanhosajustedTruthTable

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)


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