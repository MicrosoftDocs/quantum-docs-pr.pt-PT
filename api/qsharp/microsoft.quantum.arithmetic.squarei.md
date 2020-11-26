---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operação SquareI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221866"
---
# <a name="squarei-operation"></a><span data-ttu-id="b14f3-102">Operação SquareI</span><span class="sxs-lookup"><span data-stu-id="b14f3-102">SquareI operation</span></span>

<span data-ttu-id="b14f3-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b14f3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b14f3-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b14f3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b14f3-105">Calcula o quadrado do inteiro `xs` em , que deve ser zero `result` inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b14f3-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b14f3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b14f3-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b14f3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b14f3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b14f3-108">$n número de $-bit para quadrado (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b14f3-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="b14f3-109">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b14f3-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b14f3-110">Resultado de $2n$-bit (LittleEndian), deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b14f3-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b14f3-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b14f3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b14f3-112">Observações</span><span class="sxs-lookup"><span data-stu-id="b14f3-112">Remarks</span></span>

<span data-ttu-id="b14f3-113">Usa uma abordagem padrão de mudança e adição para calcular o quadrado.</span><span class="sxs-lookup"><span data-stu-id="b14f3-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="b14f3-114">Poupa $n-1$ qubits em comparação com a solução straight-forward que primeiro copia xs antes de aplicar um multiplicador regular e, em seguida, desfazer a operação de cópia.</span><span class="sxs-lookup"><span data-stu-id="b14f3-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>