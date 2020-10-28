---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: Função DeOpBEC invertida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719675"
---
# <a name="reversedopbec-function"></a><span data-ttu-id="c4594-102">Função DeOpBEC invertida</span><span class="sxs-lookup"><span data-stu-id="c4594-102">ReversedOpBEC function</span></span>

<span data-ttu-id="c4594-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c4594-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c4594-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4594-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4594-105">Dada uma operação que requer uma entrada de grande ponta, devolve uma nova operação que requer uma entrada pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="c4594-105">Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.</span></span>

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c4594-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4594-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="c4594-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="c4594-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c4594-108">A operação cuja entrada deve ser invertida.</span><span class="sxs-lookup"><span data-stu-id="c4594-108">The operation whose input is to be reversed.</span></span>



## <a name="output--littleendian--unit-ctl"></a><span data-ttu-id="c4594-109">Saída : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="c4594-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c4594-110">Uma nova operação que aceita a sua entrada como um registo de pequenas finais.</span><span class="sxs-lookup"><span data-stu-id="c4594-110">A new operation that accepts its input as a little-endian register.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4594-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c4594-111">See Also</span></span>

- [<span data-ttu-id="c4594-112">Microsoft.Quantum.Aithmetic.ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="c4594-112">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="c4594-113">Microsoft.Quantum.Aithmetic.ReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="c4594-113">Microsoft.Quantum.Arithmetic.ReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [<span data-ttu-id="c4594-114">Microsoft.Quantum.Aithmetic.ReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="c4594-114">Microsoft.Quantum.Arithmetic.ReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [<span data-ttu-id="c4594-115">Microsoft.Quantum.Aithmetic.ReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="c4594-115">Microsoft.Quantum.Arithmetic.ReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)