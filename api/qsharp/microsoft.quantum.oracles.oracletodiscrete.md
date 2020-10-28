---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Função OracleToDiscrete
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724248"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="9d2dc-102">Função OracleToDiscrete</span><span class="sxs-lookup"><span data-stu-id="9d2dc-102">OracleToDiscrete function</span></span>

<span data-ttu-id="9d2dc-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9d2dc-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9d2dc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d2dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d2dc-105">Dada uma operação que representa um oráculo "black-box", devolve um oráculo de tempo discreto que representa o oráculo "caixa preta" repetido várias vezes.</span><span class="sxs-lookup"><span data-stu-id="9d2dc-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="9d2dc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9d2dc-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="9d2dc-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="9d2dc-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9d2dc-108">A operação a ser exponencial.</span><span class="sxs-lookup"><span data-stu-id="9d2dc-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="9d2dc-109">Saída : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="9d2dc-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="9d2dc-110">Uma operação parcialmente aplicada sobre o oráculo "black-box" representando o oráculo de tempo discreto</span><span class="sxs-lookup"><span data-stu-id="9d2dc-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>