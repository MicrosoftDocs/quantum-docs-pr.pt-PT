---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223787"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="5bfcf-102">AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="5bfcf-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="5bfcf-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5bfcf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5bfcf-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5bfcf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5bfcf-105">Afirma que o qubit mais significativo de um registo qubit que representa um número inteiro não assinado está num determinado estado.</span><span class="sxs-lookup"><span data-stu-id="5bfcf-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5bfcf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5bfcf-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="5bfcf-107">valor : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="5bfcf-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="5bfcf-108">O valor da parte mais alta a ser afirmado.</span><span class="sxs-lookup"><span data-stu-id="5bfcf-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="5bfcf-109">número : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5bfcf-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5bfcf-110">Inteiro não assinado, do qual a parte mais alta é verificada.</span><span class="sxs-lookup"><span data-stu-id="5bfcf-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5bfcf-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bfcf-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5bfcf-112">Observações</span><span class="sxs-lookup"><span data-stu-id="5bfcf-112">Remarks</span></span>

<span data-ttu-id="5bfcf-113">A versão controlada desta operação ignora os controlos.</span><span class="sxs-lookup"><span data-stu-id="5bfcf-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bfcf-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5bfcf-114">See Also</span></span>

- [<span data-ttu-id="5bfcf-115">Microsoft.Quantum.Intrínseco.Assert</span><span class="sxs-lookup"><span data-stu-id="5bfcf-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)