---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: Função HTermsToGenIdx
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216018"
---
# <a name="htermstogenidx-function"></a>Função HTermsToGenIdx

Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Converte um índice para um termo Hamiltonian em `HTerm[]` formato de dados para um GeneratorIndex.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="data--hterm"></a>dados : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Inserir dados em `HTerm[]` formato.


### <a name="termtype--int"></a>termoType : [Int](xref:microsoft.quantum.lang-ref.int)[]

Informação adicional adicionada ao GeneratorIndex.


### <a name="idx--int"></a>idx : [Int](xref:microsoft.quantum.lang-ref.int)

Índice a um termo do Hamiltonian



## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um GeneratorIndex que representa um termo Hamiltoniano representado `data[idx]` por, juntamente com informações adicionais adicionadas por `termType` .