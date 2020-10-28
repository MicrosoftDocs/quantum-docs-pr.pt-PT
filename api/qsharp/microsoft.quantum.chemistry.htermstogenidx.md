---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: Função HTermsToGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714853"
---
# <a name="htermstogenidx-function"></a>Função HTermsToGenIdx

Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacote: [](https://nuget.org/packages/)


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