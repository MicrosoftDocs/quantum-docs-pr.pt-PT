---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: Função ReversedOpLEA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719639"
---
# <a name="reversedoplea-function"></a><span data-ttu-id="66911-102">Função ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="66911-102">ReversedOpLEA function</span></span>

<span data-ttu-id="66911-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="66911-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="66911-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66911-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66911-105">Dada uma operação que requer uma entrada pouco endiana, devolve uma nova operação que requer uma grande entrada de luxo.</span><span class="sxs-lookup"><span data-stu-id="66911-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="66911-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="66911-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="66911-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="66911-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="66911-108">A operação cuja entrada deve ser invertida.</span><span class="sxs-lookup"><span data-stu-id="66911-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj"></a><span data-ttu-id="66911-109">Saída : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="66911-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="66911-110">Uma nova operação que aceita a sua entrada como um registo de grandes pontas.</span><span class="sxs-lookup"><span data-stu-id="66911-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="66911-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="66911-111">See Also</span></span>

- [<span data-ttu-id="66911-112">Microsoft.Quantum.Aithmetic.ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="66911-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="66911-113">Microsoft.Quantum.Aithmetic.ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="66911-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="66911-114">Microsoft.Quantum.Aithmetic.ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="66911-114">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [<span data-ttu-id="66911-115">Microsoft.Quantum.Aithmetic.ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="66911-115">Microsoft.Quantum.Arithmetic.ReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)