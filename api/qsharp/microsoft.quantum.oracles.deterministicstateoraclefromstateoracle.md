---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854561"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle função

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte um oráculo de tipo `StateOracle` para `DeterministicStateOracle` .

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>Entrada

### <a name="idxflagqubit--int"></a>idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)

O índice para o qubit de bandeira do `stateOracle` $A$, que atua explicitamente em dois registos: a bandeira $f$ e o sistema $s$, por exemplo, $A\ket {0} \_ f\ket{\psi} \_ s$.


### <a name="stateoracle--stateoracle"></a>stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Um oráculo de preparação do estado $A de `StateOracle` tipo.



## <a name="output--deterministicstateoracle"></a>Saída : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

O mesmo oráculo de preparação estatal $A$, mas agora de `DeterministicStateOracle` tipo, por isso atua num registo onde $a,s$ já não se separam explicitamente, por exemplo.  $A\ket{0\psi} \_ {as}$.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Oracles.StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Microsoft.Quantum.Oracles.DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)