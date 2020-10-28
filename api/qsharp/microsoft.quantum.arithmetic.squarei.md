---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operação SquareI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719542"
---
# <a name="squarei-operation"></a><span data-ttu-id="b2784-102">Operação SquareI</span><span class="sxs-lookup"><span data-stu-id="b2784-102">SquareI operation</span></span>

<span data-ttu-id="b2784-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b2784-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b2784-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2784-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2784-105">Calcula o quadrado do inteiro `xs` em , que deve ser zero `result` inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b2784-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b2784-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b2784-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b2784-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b2784-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b2784-108">$n número de $-bit para quadrado (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b2784-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="b2784-109">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b2784-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b2784-110">Resultado de $2n$-bit (LittleEndian), deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b2784-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2784-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2784-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b2784-112">Observações</span><span class="sxs-lookup"><span data-stu-id="b2784-112">Remarks</span></span>

<span data-ttu-id="b2784-113">Usa uma abordagem padrão de mudança e adição para calcular o quadrado.</span><span class="sxs-lookup"><span data-stu-id="b2784-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="b2784-114">Poupa $n-1$ qubits em comparação com a solução straight-forward que primeiro copia xs antes de aplicar um multiplicador regular e, em seguida, desfazer a operação de cópia.</span><span class="sxs-lookup"><span data-stu-id="b2784-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>