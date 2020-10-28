---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operação DivideI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721222"
---
# <a name="dividei-operation"></a><span data-ttu-id="387f2-102">Operação DivideI</span><span class="sxs-lookup"><span data-stu-id="387f2-102">DivideI operation</span></span>

<span data-ttu-id="387f2-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="387f2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="387f2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="387f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="387f2-105">Divide dois inteiros quânticos.</span><span class="sxs-lookup"><span data-stu-id="387f2-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="387f2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="387f2-106">Description</span></span>

<span data-ttu-id="387f2-107">`xs` irá segurar o restante `xs - floor(xs/ys) * ys` e `result` irá aguentar `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="387f2-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="387f2-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="387f2-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="387f2-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="387f2-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="387f2-110">$n dividendo de $-bit, será substituído pelo restante.</span><span class="sxs-lookup"><span data-stu-id="387f2-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="387f2-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="387f2-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="387f2-112">divisor de $n de dólares</span><span class="sxs-lookup"><span data-stu-id="387f2-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="387f2-113">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="387f2-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="387f2-114">$n resultado de $-bit, deve estar no estado $\ket {0} $ inicialmente e será substituído pelo resultado da divisão inteiro.</span><span class="sxs-lookup"><span data-stu-id="387f2-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="387f2-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="387f2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="387f2-116">Observações</span><span class="sxs-lookup"><span data-stu-id="387f2-116">Remarks</span></span>

<span data-ttu-id="387f2-117">Usa uma abordagem padrão de mudança e subtraição para implementar a divisão.</span><span class="sxs-lookup"><span data-stu-id="387f2-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="387f2-118">A versão controlada é especializada de modo a que a subtração não exija controlos adicionais.</span><span class="sxs-lookup"><span data-stu-id="387f2-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>