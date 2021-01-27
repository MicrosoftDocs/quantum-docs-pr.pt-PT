---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operação SquareSI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842933"
---
# <a name="squaresi-operation"></a><span data-ttu-id="c8c5b-102">Operação SquareSI</span><span class="sxs-lookup"><span data-stu-id="c8c5b-102">SquareSI operation</span></span>

<span data-ttu-id="c8c5b-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c8c5b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c8c5b-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c8c5b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c8c5b-105">A Praça assinou o inteiro `xs` e armazena o resultado em , que deve ser zero `result` inicialmente.</span><span class="sxs-lookup"><span data-stu-id="c8c5b-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c8c5b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8c5b-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="c8c5b-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c8c5b-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c8c5b-108">n-bit inteiro para quadrado (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c8c5b-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="c8c5b-109">resultado : [AssinadoLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c8c5b-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c8c5b-110">Resultado de 2n-bit (SignedLittleEndian), deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="c8c5b-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8c5b-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8c5b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c8c5b-112">Observações</span><span class="sxs-lookup"><span data-stu-id="c8c5b-112">Remarks</span></span>

<span data-ttu-id="c8c5b-113">A implementação baseia-se na IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="c8c5b-113">The implementation relies on IntegerSquare.</span></span>