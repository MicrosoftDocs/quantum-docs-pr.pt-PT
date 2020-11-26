---
uid: Microsoft.Quantum.Simulation._AddGeneratorSystems
title: função _AddGeneratorSystems
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _AddGeneratorSystems
qsharp.summary: Adds two `GeneratorSystem`s to create a new `GeneratorSystem`.
ms.openlocfilehash: ffb635d7cb6c388c2158b7adb6bb872b0c77cdb1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229754"
---
# <a name="_addgeneratorsystems-function"></a>função _AddGeneratorSystems

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Adiciona dois `GeneratorSystem` s para criar um novo `GeneratorSystem` .

```qsharp
function _AddGeneratorSystems (idxTerm : Int, nTermsA : Int, nTermsB : Int, generatorIndexFunctionA : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), generatorIndexFunctionB : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="idxterm--int"></a>idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="ntermsa--int"></a>nTermsA : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="ntermsb--int"></a>nTermsB : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="generatorindexfunctiona--int---generatorindex"></a>geradorIndexFunctionA : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)




### <a name="generatorindexfunctionb--int---generatorindex"></a>geradorIndexFunctionB : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)





## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)



## <a name="remarks"></a>Observações

Este é um passo intermédio e não deve ser chamado.