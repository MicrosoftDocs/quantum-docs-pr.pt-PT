---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: Aplicação OperaçãoReversedOpBECA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 71e99d3390a2e510fd7ed28f3f6d8ed43b3ca7e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843570"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="5159b-102">Aplicação OperaçãoReversedOpBECA</span><span class="sxs-lookup"><span data-stu-id="5159b-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="5159b-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5159b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5159b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5159b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5159b-105">Aplica uma operação que leva a entrada de grande ponta a um registo que codifica um número inteiro não assinado usando um formato de pequena ponta.</span><span class="sxs-lookup"><span data-stu-id="5159b-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5159b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5159b-106">Input</span></span>

### <a name="op--bigendian--unit--is-adj--ctl"></a><span data-ttu-id="5159b-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="5159b-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5159b-108">Operação que funciona num registo de luxo.</span><span class="sxs-lookup"><span data-stu-id="5159b-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="5159b-109">registo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5159b-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5159b-110">Um pequeno registo de fim de semana para ser transformado.</span><span class="sxs-lookup"><span data-stu-id="5159b-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5159b-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5159b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5159b-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5159b-112">See Also</span></span>

- [<span data-ttu-id="5159b-113">Microsoft.Quantum.Aithmetic.ApplyReversedOpBE</span><span class="sxs-lookup"><span data-stu-id="5159b-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="5159b-114">Microsoft.Quantum.Aithmetic.ApplyReversedOpBEA</span><span class="sxs-lookup"><span data-stu-id="5159b-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="5159b-115">Microsoft.Quantum.Aithmetic.ApplyReversedOpBEC</span><span class="sxs-lookup"><span data-stu-id="5159b-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)