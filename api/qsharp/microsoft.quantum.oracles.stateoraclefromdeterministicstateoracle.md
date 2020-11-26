---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: Função StateOracleFromDeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193816"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>Função StateOracleFromDeterministicStateOracle

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte um oráculo de tipo `DeterministicStateOracle` para `StateOracle` .

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>Entrada

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Um oráculo de preparação do estado $A de `DeterministicStateOracle` tipo.



## <a name="output--stateoracle"></a>Saída : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

O mesmo oráculo de preparação do estado $A$, mas agora do `StateOracle` tipo. Note que o índice de bandeira nesta `StateOracle` é uma variável falsa e não tem efeito.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Oracles.DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft.Quantum.Oracles.StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)