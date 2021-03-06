---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: Função ReflectionOracleFromDeterministicStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842514"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>Função ReflectionOracleFromDeterministicStateOracle

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Constrói reflexão sobre um dado estado a partir de um oráculo.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Descrição

Dado um oráculo de preparação do estado determinístico representado por uma matriz unitária $O$, o resultado desta função é um oráculo que aplica uma reflexão em torno do estado $\ket{\psi}$ preparado pelo oráculo $O$; ou seja, o estado $\ket{\psi}$ tal que $O\ket {0} = \ket{\psi}$.

## <a name="input"></a>Entrada

### <a name="oracle--deterministicstateoracle"></a>oráculo : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Um oráculo que prepara cópias do estado $\ket{\psi}$.



## <a name="output--reflectionoracle"></a>Saída : [ReflexãoOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Um oráculo que reflete sobre o estado $\ket{\psi}$.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Oracles.DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft.Quantum.Oráculos.ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)