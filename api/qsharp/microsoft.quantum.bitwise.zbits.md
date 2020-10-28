---
uid: Microsoft.Quantum.Bitwise.ZBits
title: Função ZBits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718534"
---
# <a name="zbits-function"></a><span data-ttu-id="d3457-102">Função ZBits</span><span class="sxs-lookup"><span data-stu-id="d3457-102">ZBits function</span></span>

<span data-ttu-id="d3457-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="d3457-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="d3457-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3457-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3457-105">Devolve um inteiro que representa os bits Z de uma série de operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="d3457-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="d3457-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d3457-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="d3457-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d3457-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="d3457-108">Uma série de operadores pauli para ser representado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="d3457-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="d3457-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3457-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3457-110">Um inteiro $x$ com representação binária $(p_ {62} \, p_ {61} \, \pontos \, p_0)$, onde $p_i = 0$ se for `paulis[i]` `PauliI` ou `PauliX` onde $p_i = 1$ se `paulis[i]` for ou `PauliY` `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="d3457-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3457-111">Observações</span><span class="sxs-lookup"><span data-stu-id="d3457-111">Remarks</span></span>

<span data-ttu-id="d3457-112">A função será lançada se o comprimento da matriz for superior a `paulis` 63.</span><span class="sxs-lookup"><span data-stu-id="d3457-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3457-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d3457-113">See Also</span></span>

- [<span data-ttu-id="d3457-114">Microsoft.Quantum.Bitwise.XBits</span><span class="sxs-lookup"><span data-stu-id="d3457-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)