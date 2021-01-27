---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843430"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="0e96e-102">AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="0e96e-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="0e96e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0e96e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0e96e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e96e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e96e-105">Afirma que o qubit mais significativo de um registo qubit que representa um número inteiro não assinado está num determinado estado.</span><span class="sxs-lookup"><span data-stu-id="0e96e-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0e96e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0e96e-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="0e96e-107">valor : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="0e96e-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="0e96e-108">O valor da parte mais alta a ser afirmado.</span><span class="sxs-lookup"><span data-stu-id="0e96e-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="0e96e-109">número : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0e96e-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0e96e-110">Inteiro não assinado, do qual a parte mais alta é verificada.</span><span class="sxs-lookup"><span data-stu-id="0e96e-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e96e-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e96e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0e96e-112">Observações</span><span class="sxs-lookup"><span data-stu-id="0e96e-112">Remarks</span></span>

<span data-ttu-id="0e96e-113">A versão controlada desta operação ignora os controlos.</span><span class="sxs-lookup"><span data-stu-id="0e96e-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e96e-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0e96e-114">See Also</span></span>

- [<span data-ttu-id="0e96e-115">Microsoft.Quantum.Intrínseco.Assert</span><span class="sxs-lookup"><span data-stu-id="0e96e-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)