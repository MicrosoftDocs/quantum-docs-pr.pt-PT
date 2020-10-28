---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: Função HTermToGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714836"
---
# <a name="htermtogenidx-function"></a>Função HTermToGenIdx

Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacote: [](https://nuget.org/packages/)


Converte um termo Hamiltonian em `HTerm` formato de dados para um GeneratorIndex.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="term--hterm"></a>termo : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

Inserir dados em `HTerm` formato.


### <a name="termtype--int"></a>termoType : [Int](xref:microsoft.quantum.lang-ref.int)[]

Informação adicional adicionada ao GeneratorIndex.



## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um GeneratorIndex que representa um termo Hamiltoniano representado `term` por, juntamente com informações adicionais adicionadas por `termType` .