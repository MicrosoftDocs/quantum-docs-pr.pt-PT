---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operação CopyMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223294"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="a1e00-102">Operação CopyMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="a1e00-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="a1e00-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a1e00-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a1e00-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1e00-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1e00-105">Copia a parte mais significativa de um registo qubit `from` que representa um número inteiro não assinado no qubit `target` .</span><span class="sxs-lookup"><span data-stu-id="a1e00-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a1e00-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a1e00-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="a1e00-107">de: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a1e00-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a1e00-108">O inteiro não assinado do qual a parte mais alta é copiada.</span><span class="sxs-lookup"><span data-stu-id="a1e00-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="a1e00-109">o inteiro é codificado em formato pouco endiano.</span><span class="sxs-lookup"><span data-stu-id="a1e00-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a1e00-110">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a1e00-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a1e00-111">O qubit em que a parte mais alta está a ser copiada.</span><span class="sxs-lookup"><span data-stu-id="a1e00-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="a1e00-112">A codificação da broca está em base computacional.</span><span class="sxs-lookup"><span data-stu-id="a1e00-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1e00-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1e00-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a1e00-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a1e00-114">See Also</span></span>

- [<span data-ttu-id="a1e00-115">Microsoft.Quantum.Aritmetic.LittleEndian</span><span class="sxs-lookup"><span data-stu-id="a1e00-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)