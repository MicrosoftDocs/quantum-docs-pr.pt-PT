---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Função OracleToDiscrete
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842543"
---
# <a name="oracletodiscrete-function"></a>Função OracleToDiscrete

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma operação que representa um oráculo "black-box", devolve um oráculo de tempo discreto que representa o oráculo "caixa preta" repetido várias vezes.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Entrada

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

A operação a ser exponencial.



## <a name="output--discreteoracle"></a>Saída : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Uma operação parcialmente aplicada sobre o oráculo "black-box" representando o oráculo de tempo discreto

## <a name="example"></a>Exemplo

`OracleToDiscrete(U)(3, target)` é equivalente a `U(target)` repetido três vezes.