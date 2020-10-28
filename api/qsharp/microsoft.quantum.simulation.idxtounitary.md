---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: Função IdxToUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: a142d8a5af56a43de6341e3c0bdc77f50030f06e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710597"
---
# <a name="idxtounitary-function"></a>Função IdxToUnitary

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Usado na implementação de `PauliBlockEncoding`

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="idx--int"></a>idx : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="genfun--int---generatorindex"></a>genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)




### <a name="genidxtounitary--generatorindex---qubit--unit-adj--ctl"></a>genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl





## <a name="output--qubit--unit-adj--ctl"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.PauliBlockEncoding](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)