---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: função _ZTermToPauliGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 1569ec742778549b8754cdca8b2d9872310e8976
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714178"
---
# <a name="_ztermtopauligenidx-function"></a>função _ZTermToPauliGenIdx

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Converte um GeneratorIndex descrevendo um termo Z com uma expressão 'GeneratorIndex[]' em termos de Paulis.

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>Entrada

### <a name="term--generatorindex"></a>termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` representando um termo Z.



## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

'GeneratorIndex[]' expressando o termo Z como termos Pauli.