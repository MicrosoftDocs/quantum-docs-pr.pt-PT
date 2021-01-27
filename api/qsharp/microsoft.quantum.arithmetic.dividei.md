---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operação DivideI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846690"
---
# <a name="dividei-operation"></a><span data-ttu-id="2fd2b-102">Operação DivideI</span><span class="sxs-lookup"><span data-stu-id="2fd2b-102">DivideI operation</span></span>

<span data-ttu-id="2fd2b-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2fd2b-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="2fd2b-105">Divide dois inteiros quânticos.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2fd2b-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="2fd2b-106">Description</span></span>

<span data-ttu-id="2fd2b-107">`xs` irá segurar o restante `xs - floor(xs/ys) * ys` e `result` irá aguentar `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="2fd2b-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="2fd2b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2fd2b-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="2fd2b-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2fd2b-110">$n dividendo de $-bit, será substituído pelo restante.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="2fd2b-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2fd2b-112">divisor de $n de dólares</span><span class="sxs-lookup"><span data-stu-id="2fd2b-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="2fd2b-113">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2fd2b-114">$n resultado de $-bit, deve estar no estado $\ket {0} $ inicialmente e será substituído pelo resultado da divisão inteiro.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fd2b-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2fd2b-116">Observações</span><span class="sxs-lookup"><span data-stu-id="2fd2b-116">Remarks</span></span>

<span data-ttu-id="2fd2b-117">Usa uma abordagem padrão de mudança e subtraição para implementar a divisão.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="2fd2b-118">A versão controlada é especializada de modo a que a subtração não exija controlos adicionais.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>