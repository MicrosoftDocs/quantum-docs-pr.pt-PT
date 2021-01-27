---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: Função Determinística Determinística
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: c7aa80feda67d68216f318073ee8c6a5eb0653c0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854516"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="6dd02-102">Função Determinística Determinística</span><span class="sxs-lookup"><span data-stu-id="6dd02-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="6dd02-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="6dd02-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="6dd02-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6dd02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6dd02-105">Combina os oráculos `DeterministicStateOracle` `ObliviousOracle` e.</span><span class="sxs-lookup"><span data-stu-id="6dd02-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="6dd02-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6dd02-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="6dd02-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="6dd02-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="6dd02-108">Um oráculo de preparação do estado $A$ do tipo `DeterministicStateOracle` agindo no registo $a$.</span><span class="sxs-lookup"><span data-stu-id="6dd02-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="6dd02-109">signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="6dd02-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="6dd02-110">Um oráculo $U$ do tipo `ObliviousOracle` agindo conjuntamente no registo $a,s$.</span><span class="sxs-lookup"><span data-stu-id="6dd02-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="6dd02-111">Saída : [Ócle Do esquecimento](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="6dd02-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="6dd02-112">Um oráculo $O=UA$ do `ObliviousOracle` tipo.</span><span class="sxs-lookup"><span data-stu-id="6dd02-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dd02-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6dd02-113">See Also</span></span>

- [<span data-ttu-id="6dd02-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="6dd02-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="6dd02-115">Microsoft.Quantum.Oráculos.IgnoróuoOracle</span><span class="sxs-lookup"><span data-stu-id="6dd02-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)