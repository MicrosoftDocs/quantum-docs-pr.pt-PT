---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operação DivideI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223311"
---
# <a name="dividei-operation"></a><span data-ttu-id="96ed0-102">Operação DivideI</span><span class="sxs-lookup"><span data-stu-id="96ed0-102">DivideI operation</span></span>

<span data-ttu-id="96ed0-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="96ed0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="96ed0-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="96ed0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="96ed0-105">Divide dois inteiros quânticos.</span><span class="sxs-lookup"><span data-stu-id="96ed0-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="96ed0-106">Description</span><span class="sxs-lookup"><span data-stu-id="96ed0-106">Description</span></span>

<span data-ttu-id="96ed0-107">`xs` irá segurar o restante `xs - floor(xs/ys) * ys` e `result` irá aguentar `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="96ed0-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="96ed0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="96ed0-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="96ed0-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="96ed0-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="96ed0-110">$n dividendo de $-bit, será substituído pelo restante.</span><span class="sxs-lookup"><span data-stu-id="96ed0-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="96ed0-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="96ed0-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="96ed0-112">divisor de $n de dólares</span><span class="sxs-lookup"><span data-stu-id="96ed0-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="96ed0-113">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="96ed0-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="96ed0-114">$n resultado de $-bit, deve estar no estado $\ket {0} $ inicialmente e será substituído pelo resultado da divisão inteiro.</span><span class="sxs-lookup"><span data-stu-id="96ed0-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="96ed0-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96ed0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="96ed0-116">Observações</span><span class="sxs-lookup"><span data-stu-id="96ed0-116">Remarks</span></span>

<span data-ttu-id="96ed0-117">Usa uma abordagem padrão de mudança e subtraição para implementar a divisão.</span><span class="sxs-lookup"><span data-stu-id="96ed0-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="96ed0-118">A versão controlada é especializada de modo a que a subtração não exija controlos adicionais.</span><span class="sxs-lookup"><span data-stu-id="96ed0-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>