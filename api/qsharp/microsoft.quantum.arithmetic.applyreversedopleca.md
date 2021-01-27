---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA
title: Aplicar operaçãoReversedOpLECA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLECA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: d0d444afcc1fa760f3035101e82cf8043c6541c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843486"
---
# <a name="applyreversedopleca-operation"></a><span data-ttu-id="f952a-102">Aplicar operaçãoReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="f952a-102">ApplyReversedOpLECA operation</span></span>

<span data-ttu-id="f952a-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f952a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f952a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f952a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f952a-105">Aplica uma operação que leva a entrada pouco endiana a um registo que codifica um número inteiro não assinado usando o formato de grande ponta.</span><span class="sxs-lookup"><span data-stu-id="f952a-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f952a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f952a-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="f952a-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="f952a-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f952a-108">Operação que atua num registo de luxo.</span><span class="sxs-lookup"><span data-stu-id="f952a-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="f952a-109">registo : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="f952a-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="f952a-110">Um grande registo de luxo para ser transformado.</span><span class="sxs-lookup"><span data-stu-id="f952a-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f952a-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f952a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f952a-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f952a-112">See Also</span></span>

- [<span data-ttu-id="f952a-113">Microsoft.Quantum.Aithmetic.ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="f952a-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="f952a-114">Microsoft.Quantum.Aithmetic.ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="f952a-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="f952a-115">Microsoft.Quantum.Aithmetic.ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="f952a-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)