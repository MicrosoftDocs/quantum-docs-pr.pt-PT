---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: Função StateOracleFromDeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724220"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="d1860-102">Função StateOracleFromDeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="d1860-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="d1860-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d1860-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d1860-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1860-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1860-105">Converte um oráculo de tipo `DeterministicStateOracle` para `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="d1860-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="d1860-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1860-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="d1860-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="d1860-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="d1860-108">Um oráculo de preparação do estado $A de `DeterministicStateOracle` tipo.</span><span class="sxs-lookup"><span data-stu-id="d1860-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="d1860-109">Saída : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="d1860-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="d1860-110">O mesmo oráculo de preparação do estado $A$, mas agora do `StateOracle` tipo.</span><span class="sxs-lookup"><span data-stu-id="d1860-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="d1860-111">Note que o índice de bandeira nesta `StateOracle` é uma variável falsa e não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="d1860-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1860-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d1860-112">See Also</span></span>

- [<span data-ttu-id="d1860-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="d1860-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="d1860-114">Microsoft.Quantum.Oracles.StateOracle</span><span class="sxs-lookup"><span data-stu-id="d1860-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)