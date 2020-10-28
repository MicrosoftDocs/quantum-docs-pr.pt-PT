---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721379"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="f2a3e-102">AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="f2a3e-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="f2a3e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f2a3e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f2a3e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2a3e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2a3e-105">Afirma que o qubit mais significativo de um registo qubit que representa um número inteiro não assinado está num determinado estado.</span><span class="sxs-lookup"><span data-stu-id="f2a3e-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f2a3e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f2a3e-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="f2a3e-107">valor : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="f2a3e-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="f2a3e-108">O valor da parte mais alta a ser afirmado.</span><span class="sxs-lookup"><span data-stu-id="f2a3e-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="f2a3e-109">número : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f2a3e-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f2a3e-110">Inteiro não assinado, do qual a parte mais alta é verificada.</span><span class="sxs-lookup"><span data-stu-id="f2a3e-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2a3e-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2a3e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f2a3e-112">Observações</span><span class="sxs-lookup"><span data-stu-id="f2a3e-112">Remarks</span></span>

<span data-ttu-id="f2a3e-113">A versão controlada desta operação ignora os controlos.</span><span class="sxs-lookup"><span data-stu-id="f2a3e-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2a3e-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f2a3e-114">See Also</span></span>

- [<span data-ttu-id="f2a3e-115">Microsoft.Quantum.Intrínseco.Assert</span><span class="sxs-lookup"><span data-stu-id="f2a3e-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)