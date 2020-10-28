---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _Função V0123TermToPauliGenIdx_
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: b522691d6826933122e2ebac051b15e35b9902e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714206"
---
# <a name="_v0123termtopauligenidx_-function"></a>_Função V0123TermToPauliGenIdx_

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Converte um GeneratorIndex descrevendo um termo PQRS com uma expressão 'GeneratorIndex[]' em termos de Paulis

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>Entrada

### <a name="term--generatorindex"></a>termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` representando um termo PQRS.



## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

'GeneratorIndex[]' expressando o termo PQRS como termos Pauli.