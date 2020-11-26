---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: Aplicação OperaçãoReversedOpBEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 3a5fef3bb4549433540b2a7b5e94d3cd2d527639
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202775"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="3f3c2-102">Aplicação OperaçãoReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="3f3c2-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="3f3c2-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3f3c2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3f3c2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f3c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f3c2-105">Aplica uma operação que leva a entrada de grande ponta a um registo que codifica um número inteiro não assinado usando um formato de pequena ponta.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="3f3c2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3f3c2-106">Input</span></span>

### <a name="op--bigendian--unit--is-ctl"></a><span data-ttu-id="3f3c2-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="3f3c2-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3f3c2-108">Operação que funciona num registo de luxo.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="3f3c2-109">registo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f3c2-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f3c2-110">Um pequeno registo de fim de semana para ser transformado.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f3c2-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f3c2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3f3c2-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3f3c2-112">See Also</span></span>

- [<span data-ttu-id="3f3c2-113">Microsoft.Quantum.Aithmetic.ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="3f3c2-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="3f3c2-114">Microsoft.Quantum.Aithmetic.ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="3f3c2-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="3f3c2-115">Microsoft.Quantum.Aithmetic.ApplyReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="3f3c2-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)