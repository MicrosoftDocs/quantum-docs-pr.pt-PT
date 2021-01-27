---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Função TamanhosajustedTruthTable
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855326"
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