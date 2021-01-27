---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: Função HTermsToGenIdx
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839636"
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