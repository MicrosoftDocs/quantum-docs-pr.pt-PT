---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Operação AddI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191028"
---
# <a name="addi-operation"></a><span data-ttu-id="991aa-102">Operação AddI</span><span class="sxs-lookup"><span data-stu-id="991aa-102">AddI operation</span></span>

<span data-ttu-id="991aa-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="991aa-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="991aa-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="991aa-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="991aa-105">Escolhe automaticamente entre adição com transporte e sem, dependendo do tamanho do registo de `ys` .</span><span class="sxs-lookup"><span data-stu-id="991aa-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="991aa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="991aa-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="991aa-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="991aa-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="991aa-108">$n adenda de $-bit.</span><span class="sxs-lookup"><span data-stu-id="991aa-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="991aa-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="991aa-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="991aa-110">Adicione com pelo menos $n$ qubits.</span><span class="sxs-lookup"><span data-stu-id="991aa-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="991aa-111">Vai segurar o resultado.</span><span class="sxs-lookup"><span data-stu-id="991aa-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="991aa-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="991aa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

