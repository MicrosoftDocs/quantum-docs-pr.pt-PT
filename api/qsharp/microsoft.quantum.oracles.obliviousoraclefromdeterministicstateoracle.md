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
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="e94c0-102">Função Determinística Determinística</span><span class="sxs-lookup"><span data-stu-id="e94c0-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="e94c0-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e94c0-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e94c0-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e94c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e94c0-105">Combina os oráculos `DeterministicStateOracle` `ObliviousOracle` e.</span><span class="sxs-lookup"><span data-stu-id="e94c0-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="e94c0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e94c0-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="e94c0-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="e94c0-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="e94c0-108">Um oráculo de preparação do estado $A$ do tipo `DeterministicStateOracle` agindo no registo $a$.</span><span class="sxs-lookup"><span data-stu-id="e94c0-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="e94c0-109">signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="e94c0-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="e94c0-110">Um oráculo $U$ do tipo `ObliviousOracle` agindo conjuntamente no registo $a,s$.</span><span class="sxs-lookup"><span data-stu-id="e94c0-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="e94c0-111">Saída : [Ócle Do esquecimento](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="e94c0-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="e94c0-112">Um oráculo $O=UA$ do `ObliviousOracle` tipo.</span><span class="sxs-lookup"><span data-stu-id="e94c0-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e94c0-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e94c0-113">See Also</span></span>

- [<span data-ttu-id="e94c0-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="e94c0-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="e94c0-115">Microsoft.Quantum.Oráculos.IgnoróuoOracle</span><span class="sxs-lookup"><span data-stu-id="e94c0-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)