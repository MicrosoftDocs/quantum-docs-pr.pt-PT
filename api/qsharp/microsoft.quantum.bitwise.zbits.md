---
uid: Microsoft.Quantum.Bitwise.ZBits
title: Função ZBits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842065"
---
# <a name="zbits-function"></a><span data-ttu-id="3cb5b-102">Função ZBits</span><span class="sxs-lookup"><span data-stu-id="3cb5b-102">ZBits function</span></span>

<span data-ttu-id="3cb5b-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="3cb5b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="3cb5b-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3cb5b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3cb5b-105">Devolve um inteiro que representa os bits Z de uma série de operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="3cb5b-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="3cb5b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3cb5b-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="3cb5b-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="3cb5b-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="3cb5b-108">Uma série de operadores pauli para ser representado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="3cb5b-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="3cb5b-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3cb5b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3cb5b-110">Um inteiro $x$ com representação binária $(p_ {62} \, p_ {61} \, \pontos \, p_0)$, onde $p_i = 0$ se for `paulis[i]` `PauliI` ou `PauliX` onde $p_i = 1$ se `paulis[i]` for ou `PauliY` `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="3cb5b-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3cb5b-111">Observações</span><span class="sxs-lookup"><span data-stu-id="3cb5b-111">Remarks</span></span>

<span data-ttu-id="3cb5b-112">A função será lançada se o comprimento da matriz for superior a `paulis` 63.</span><span class="sxs-lookup"><span data-stu-id="3cb5b-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cb5b-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3cb5b-113">See Also</span></span>

- [<span data-ttu-id="3cb5b-114">Microsoft.Quantum.Bitwise.XBits</span><span class="sxs-lookup"><span data-stu-id="3cb5b-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)