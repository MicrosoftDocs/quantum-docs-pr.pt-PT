---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: Função ReversedOpBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 170f63e60e6c26dbdd33af02c6a3387a1b3dbc44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719699"
---
# <a name="reversedopbe-function"></a><span data-ttu-id="da403-102">Função ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="da403-102">ReversedOpBE function</span></span>

<span data-ttu-id="da403-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="da403-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="da403-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da403-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da403-105">Dada uma operação que requer uma entrada de grande ponta, devolve uma nova operação que requer uma entrada pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="da403-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a><span data-ttu-id="da403-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="da403-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="da403-107">op : [Unidade BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da403-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="da403-108">A operação cuja entrada deve ser invertida.</span><span class="sxs-lookup"><span data-stu-id="da403-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit"></a><span data-ttu-id="da403-109">Saída : [Unidade LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da403-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="da403-110">Uma nova operação que aceita a sua entrada como um registo de pequenas finais.</span><span class="sxs-lookup"><span data-stu-id="da403-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="da403-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="da403-111">See Also</span></span>

- [<span data-ttu-id="da403-112">Microsoft.Quantum.Aithmetic.ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="da403-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="da403-113">Microsoft.Quantum.Aithmetic.ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="da403-113">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="da403-114">Microsoft.Quantum.Aithmetic.ReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="da403-114">Microsoft.Quantum.Arithmetic.ReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [<span data-ttu-id="da403-115">Microsoft.Quantum.Aithmetic.ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="da403-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)