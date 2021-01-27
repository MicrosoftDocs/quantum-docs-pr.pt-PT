---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: AplicarOperaçãoReversedOpLEC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 74ecc705a6e3d1d59c4c4ae71d30171c12fa45ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843508"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="b1340-102">AplicarOperaçãoReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="b1340-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="b1340-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b1340-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b1340-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1340-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1340-105">Aplica uma operação que leva a entrada pouco endiana a um registo que codifica um número inteiro não assinado usando o formato de grande ponta.</span><span class="sxs-lookup"><span data-stu-id="b1340-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="b1340-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b1340-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="b1340-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="b1340-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b1340-108">Operação que atua num registo de luxo.</span><span class="sxs-lookup"><span data-stu-id="b1340-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="b1340-109">registo : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="b1340-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="b1340-110">Um grande registo de luxo para ser transformado.</span><span class="sxs-lookup"><span data-stu-id="b1340-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1340-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1340-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b1340-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b1340-112">See Also</span></span>

- [<span data-ttu-id="b1340-113">Microsoft.Quantum.Aithmetic.ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="b1340-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="b1340-114">Microsoft.Quantum.Aithmetic.ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="b1340-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="b1340-115">Microsoft.Quantum.Aithmetic.ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="b1340-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)