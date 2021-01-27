---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: função _ComputeJordanWignerBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839533"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="a7f03-102">função _ComputeJordanWignerBitString</span><span class="sxs-lookup"><span data-stu-id="a7f03-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="a7f03-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a7f03-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a7f03-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a7f03-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a7f03-105">Computes Z componente da cadeia Jordan-Wigner entre índices de fermiion em um operador fermiónico com um número par de operadores de criação/aniquilação.</span><span class="sxs-lookup"><span data-stu-id="a7f03-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="a7f03-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a7f03-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="a7f03-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a7f03-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a7f03-108">O Número de fermiões no sistema.</span><span class="sxs-lookup"><span data-stu-id="a7f03-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="a7f03-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a7f03-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a7f03-110">índices de operador fermiónico.</span><span class="sxs-lookup"><span data-stu-id="a7f03-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a7f03-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a7f03-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a7f03-112">Mordendo `Bool[]` é `true` onde um `PauliZ` deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="a7f03-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="a7f03-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a7f03-113">Example</span></span>

<span data-ttu-id="a7f03-114">deixe o bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]; bitString é [falso, falso, falso ,verdadeiro, verdadeiro, verdadeiro, falso].</span><span class="sxs-lookup"><span data-stu-id="a7f03-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>