---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA
title: Aplicar operaçãoReversedOpBEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 17d05e0914eead28ff0e04b858b003659d37ab7f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202826"
---
# <a name="applyreversedopbea-operation"></a><span data-ttu-id="d49f1-102">Aplicar operaçãoReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="d49f1-102">ApplyReversedOpBEA operation</span></span>

<span data-ttu-id="d49f1-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d49f1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d49f1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d49f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d49f1-105">Aplica uma operação que leva a entrada de grande ponta a um registo que codifica um número inteiro não assinado usando um formato de pequena ponta.</span><span class="sxs-lookup"><span data-stu-id="d49f1-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d49f1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d49f1-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj"></a><span data-ttu-id="d49f1-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="d49f1-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d49f1-108">Operação que funciona num registo de luxo.</span><span class="sxs-lookup"><span data-stu-id="d49f1-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="d49f1-109">registo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d49f1-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d49f1-110">Um pequeno registo de fim de semana para ser transformado.</span><span class="sxs-lookup"><span data-stu-id="d49f1-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d49f1-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d49f1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d49f1-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d49f1-112">See Also</span></span>

- [<span data-ttu-id="d49f1-113">Microsoft.Quantum.Aithmetic.ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="d49f1-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="d49f1-114">Microsoft.Quantum.Aithmetic.ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="d49f1-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="d49f1-115">Microsoft.Quantum.Aithmetic.ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="d49f1-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)