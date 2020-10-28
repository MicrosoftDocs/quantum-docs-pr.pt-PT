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
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="55fa8-102">DeterministicStateOracleFromStateOracle função</span><span class="sxs-lookup"><span data-stu-id="55fa8-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="55fa8-103">Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="55fa8-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="55fa8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55fa8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55fa8-105">Converte um oráculo de tipo `StateOracle` para `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="55fa8-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="55fa8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="55fa8-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="55fa8-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55fa8-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55fa8-108">O índice para o qubit de bandeira do `stateOracle` $A$, que atua explicitamente em dois registos: a bandeira $f$ e o sistema $s$, por exemplo, $A\ket {0} \_ f\ket{\psi} \_ s$.</span><span class="sxs-lookup"><span data-stu-id="55fa8-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="55fa8-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="55fa8-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="55fa8-110">Um oráculo de preparação do estado $A de `StateOracle` tipo.</span><span class="sxs-lookup"><span data-stu-id="55fa8-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="55fa8-111">Saída : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="55fa8-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="55fa8-112">O mesmo oráculo de preparação estatal $A$, mas agora de `DeterministicStateOracle` tipo, por isso atua num registo onde $a,s$ já não se separam explicitamente, por exemplo.  $A\ket{0\psi} \_ {as}$.</span><span class="sxs-lookup"><span data-stu-id="55fa8-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="55fa8-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="55fa8-113">See Also</span></span>

- [<span data-ttu-id="55fa8-114">Microsoft.Quantum.Oracles.StateOracle</span><span class="sxs-lookup"><span data-stu-id="55fa8-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="55fa8-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="55fa8-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)