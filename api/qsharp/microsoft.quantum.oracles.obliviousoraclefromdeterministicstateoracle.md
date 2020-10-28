---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: Função Determinística Determinística
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722221"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a>Função Determinística Determinística

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [](https://nuget.org/packages/)


Combina os oráculos `DeterministicStateOracle` `ObliviousOracle` e.

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a>Entrada

### <a name="ancillaoracle--deterministicstateoracle"></a>ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Um oráculo de preparação do estado $A$ do tipo `DeterministicStateOracle` agindo no registo $a$.


### <a name="signaloracle--obliviousoracle"></a>signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Um oráculo $U$ do tipo `ObliviousOracle` agindo conjuntamente no registo $a,s$.



## <a name="output--obliviousoracle"></a>Saída : [Ócle Do esquecimento](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Um oráculo $O=UA$ do `ObliviousOracle` tipo.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Oracles.DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft.Quantum.Oráculos.IgnoróuoOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)