---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: Função ReversedOpBEA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719698"
---
# <a name="reversedopbea-function"></a><span data-ttu-id="f3ad3-102">Função ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="f3ad3-102">ReversedOpBEA function</span></span>

<span data-ttu-id="f3ad3-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f3ad3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f3ad3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3ad3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3ad3-105">Dada uma operação que requer uma entrada de grande ponta, devolve uma nova operação que requer uma entrada pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="f3ad3-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="f3ad3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f3ad3-106">Input</span></span>

### <a name="op--bigendian--unit-adj"></a><span data-ttu-id="f3ad3-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="f3ad3-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f3ad3-108">A operação cuja entrada deve ser invertida.</span><span class="sxs-lookup"><span data-stu-id="f3ad3-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj"></a><span data-ttu-id="f3ad3-109">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="f3ad3-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f3ad3-110">Uma nova operação que aceita a sua entrada como um registo de pequenas finais.</span><span class="sxs-lookup"><span data-stu-id="f3ad3-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3ad3-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f3ad3-111">See Also</span></span>

- [<span data-ttu-id="f3ad3-112">Microsoft.Quantum.Aithmetic.ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="f3ad3-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="f3ad3-113">Microsoft.Quantum.Aithmetic.ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="f3ad3-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="f3ad3-114">Microsoft.Quantum.Aithmetic.ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="f3ad3-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="f3ad3-115">Microsoft.Quantum.Aithmetic.ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="f3ad3-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)