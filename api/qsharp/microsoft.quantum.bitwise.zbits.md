---
uid: Microsoft.Quantum.Bitwise.ZBits
title: Função ZBits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219452"
---
# <a name="zbits-function"></a><span data-ttu-id="cfb79-102">Função ZBits</span><span class="sxs-lookup"><span data-stu-id="cfb79-102">ZBits function</span></span>

<span data-ttu-id="cfb79-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="cfb79-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="cfb79-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cfb79-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cfb79-105">Devolve um inteiro que representa os bits Z de uma série de operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="cfb79-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="cfb79-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cfb79-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="cfb79-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="cfb79-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="cfb79-108">Uma série de operadores pauli para ser representado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="cfb79-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="cfb79-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cfb79-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cfb79-110">Um inteiro $x$ com representação binária $(p_ {62} \, p_ {61} \, \pontos \, p_0)$, onde $p_i = 0$ se for `paulis[i]` `PauliI` ou `PauliX` onde $p_i = 1$ se `paulis[i]` for ou `PauliY` `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="cfb79-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfb79-111">Observações</span><span class="sxs-lookup"><span data-stu-id="cfb79-111">Remarks</span></span>

<span data-ttu-id="cfb79-112">A função será lançada se o comprimento da matriz for superior a `paulis` 63.</span><span class="sxs-lookup"><span data-stu-id="cfb79-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfb79-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cfb79-113">See Also</span></span>

- [<span data-ttu-id="cfb79-114">Microsoft.Quantum.Bitwise.XBits</span><span class="sxs-lookup"><span data-stu-id="cfb79-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)