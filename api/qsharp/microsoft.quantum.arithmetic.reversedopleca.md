---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: Função ReversedOpLECA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: b5413e43ad50ba7252705ef53b21e63650dbb2a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719615"
---
# <a name="reversedopleca-function"></a><span data-ttu-id="77c8e-102">Função ReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="77c8e-102">ReversedOpLECA function</span></span>

<span data-ttu-id="77c8e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="77c8e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="77c8e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77c8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77c8e-105">Dada uma operação que requer uma entrada pouco endiana, devolve uma nova operação que requer uma grande entrada de luxo.</span><span class="sxs-lookup"><span data-stu-id="77c8e-105">Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.</span></span>

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="77c8e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="77c8e-106">Input</span></span>

### <a name="op--littleendian--unit-adj--ctl"></a><span data-ttu-id="77c8e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="77c8e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="77c8e-108">A operação cuja entrada deve ser invertida.</span><span class="sxs-lookup"><span data-stu-id="77c8e-108">The operation whose input is to be reversed.</span></span>



## <a name="output--bigendian--unit-adj--ctl"></a><span data-ttu-id="77c8e-109">Saída : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="77c8e-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="77c8e-110">Uma nova operação que aceita a sua entrada como um registo de grandes pontas.</span><span class="sxs-lookup"><span data-stu-id="77c8e-110">A new operation that accepts its input as a big-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="77c8e-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="77c8e-111">See Also</span></span>

- [<span data-ttu-id="77c8e-112">Microsoft.Quantum.Aithmetic.ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="77c8e-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [<span data-ttu-id="77c8e-113">Microsoft.Quantum.Aithmetic.ReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="77c8e-113">Microsoft.Quantum.Arithmetic.ReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [<span data-ttu-id="77c8e-114">Microsoft.Quantum.Aithmetic.ReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="77c8e-114">Microsoft.Quantum.Arithmetic.ReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [<span data-ttu-id="77c8e-115">Microsoft.Quantum.Aithmetic.ReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="77c8e-115">Microsoft.Quantum.Arithmetic.ReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)