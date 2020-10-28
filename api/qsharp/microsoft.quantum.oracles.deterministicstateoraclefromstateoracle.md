---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724251"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle função

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [](https://nuget.org/packages/)


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