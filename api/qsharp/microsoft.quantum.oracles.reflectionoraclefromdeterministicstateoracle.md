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
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="44475-102">Função ReflectionOracleFromDeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="44475-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="44475-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="44475-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="44475-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44475-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44475-105">Constrói reflexão sobre um dado estado a partir de um oráculo.</span><span class="sxs-lookup"><span data-stu-id="44475-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="44475-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="44475-106">Description</span></span>

<span data-ttu-id="44475-107">Dado um oráculo de preparação do estado determinístico representado por uma matriz unitária $O$, o resultado desta função é um oráculo que aplica uma reflexão em torno do estado $\ket{\psi}$ preparado pelo oráculo $O$; ou seja, o estado $\ket{\psi}$ tal que $O\ket {0} = \ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="44475-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="44475-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="44475-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="44475-109">oráculo : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="44475-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="44475-110">Um oráculo que prepara cópias do estado $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="44475-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="44475-111">Saída : [ReflexãoOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="44475-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="44475-112">Um oráculo que reflete sobre o estado $\ket{\psi}$.</span><span class="sxs-lookup"><span data-stu-id="44475-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="44475-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="44475-113">See Also</span></span>

- [<span data-ttu-id="44475-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="44475-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="44475-115">Microsoft.Quantum.Oráculos.ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="44475-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)