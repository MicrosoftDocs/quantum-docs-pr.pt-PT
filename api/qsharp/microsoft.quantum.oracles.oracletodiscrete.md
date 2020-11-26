---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Função OracleToDiscrete
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193850"
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