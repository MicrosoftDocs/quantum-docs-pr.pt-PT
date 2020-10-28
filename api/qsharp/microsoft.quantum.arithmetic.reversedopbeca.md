---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBECA
title: Função ReversedOpBECA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBECA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5617e191260903ac25effc8b922810932b7dc505
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719663"
---
# <a name="reversedopbeca-function"></a><span data-ttu-id="8119b-102">Função ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="8119b-102">ReversedOpBECA function</span></span>

<span data-ttu-id="8119b-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8119b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8119b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8119b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8119b-105">Dada uma operação que requer uma entrada de grande ponta, devolve uma nova operação que requer uma entrada pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="8119b-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="8119b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8119b-106">Input</span></span>

### <a name="op--bigendian--unit-adj--ctl"></a><span data-ttu-id="8119b-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8119b-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8119b-108">A operação cuja entrada deve ser invertida.</span><span class="sxs-lookup"><span data-stu-id="8119b-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="8119b-109">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8119b-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="8119b-110">Uma nova operação que aceita a sua entrada como um registo de pequenas finais.</span><span class="sxs-lookup"><span data-stu-id="8119b-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="8119b-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8119b-111">See Also</span></span>

- [<span data-ttu-id="8119b-112">Microsoft.Quantum.Aithmetic.ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="8119b-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)
- [<span data-ttu-id="8119b-113">Microsoft.Quantum.Aithmetic.ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="8119b-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="8119b-114">Microsoft.Quantum.Aithmetic.ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="8119b-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="8119b-115">Microsoft.Quantum.Aithmetic.ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="8119b-115">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)