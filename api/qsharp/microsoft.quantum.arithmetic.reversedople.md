---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: Função ReversedOpLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 6ebc4e97cb6d515e99e85922d03ca246b56084ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719650"
---
# <a name="reversedople-function"></a><span data-ttu-id="7c5c3-102">Função ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="7c5c3-102">ReversedOpLE function</span></span>

<span data-ttu-id="7c5c3-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7c5c3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7c5c3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c5c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c5c3-105">Dada uma operação que requer uma entrada pouco endiana, devolve uma nova operação que requer uma grande entrada de luxo.</span><span class="sxs-lookup"><span data-stu-id="7c5c3-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="7c5c3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7c5c3-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="7c5c3-107">op : [Unidade LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c5c3-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7c5c3-108">A operação cuja entrada deve ser invertida.</span><span class="sxs-lookup"><span data-stu-id="7c5c3-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit"></a><span data-ttu-id="7c5c3-109">Saída : [Unidade BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c5c3-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7c5c3-110">Uma nova operação que aceita a sua entrada como um registo de grandes pontas.</span><span class="sxs-lookup"><span data-stu-id="7c5c3-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c5c3-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7c5c3-111">See Also</span></span>

- [<span data-ttu-id="7c5c3-112">Microsoft.Quantum.Aithmetic.ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="7c5c3-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="7c5c3-113">Microsoft.Quantum.Aithmetic.ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="7c5c3-113">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="7c5c3-114">Microsoft.Quantum.Aithmetic.ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="7c5c3-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="7c5c3-115">Microsoft.Quantum.Aithmetic.ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="7c5c3-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)