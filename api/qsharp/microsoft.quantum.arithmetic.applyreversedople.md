---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: AplicarOperaçãoReversedOpLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 16ce6842cdef8e519a13a45640edc3d79cdbce25
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202758"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="95f9e-102">AplicarOperaçãoReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="95f9e-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="95f9e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="95f9e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="95f9e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="95f9e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="95f9e-105">Aplica uma operação que leva a entrada pouco endiana a um registo que codifica um número inteiro não assinado usando o formato de grande ponta.</span><span class="sxs-lookup"><span data-stu-id="95f9e-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="95f9e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="95f9e-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="95f9e-107">op : [Unidade LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95f9e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="95f9e-108">Operação que atua num registo de luxo.</span><span class="sxs-lookup"><span data-stu-id="95f9e-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="95f9e-109">registo : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="95f9e-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="95f9e-110">Um grande registo de luxo para ser transformado.</span><span class="sxs-lookup"><span data-stu-id="95f9e-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95f9e-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95f9e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="95f9e-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="95f9e-112">See Also</span></span>

- [<span data-ttu-id="95f9e-113">Microsoft.Quantum.Aithmetic.ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="95f9e-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="95f9e-114">Microsoft.Quantum.Aithmetic.ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="95f9e-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="95f9e-115">Microsoft.Quantum.Aithmetic.ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="95f9e-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)