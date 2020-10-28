---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operação SquareSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719531"
---
# <a name="squaresi-operation"></a><span data-ttu-id="7e9ae-102">Operação SquareSI</span><span class="sxs-lookup"><span data-stu-id="7e9ae-102">SquareSI operation</span></span>

<span data-ttu-id="7e9ae-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7e9ae-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7e9ae-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e9ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e9ae-105">A Praça assinou o inteiro `xs` e armazena o resultado em , que deve ser zero `result` inicialmente.</span><span class="sxs-lookup"><span data-stu-id="7e9ae-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7e9ae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7e9ae-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="7e9ae-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7e9ae-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="7e9ae-108">n-bit inteiro para quadrado (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7e9ae-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="7e9ae-109">resultado : [AssinadoLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7e9ae-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="7e9ae-110">Resultado de 2n-bit (SignedLittleEndian), deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="7e9ae-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e9ae-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e9ae-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7e9ae-112">Observações</span><span class="sxs-lookup"><span data-stu-id="7e9ae-112">Remarks</span></span>

<span data-ttu-id="7e9ae-113">A implementação baseia-se na IntegerSquare.</span><span class="sxs-lookup"><span data-stu-id="7e9ae-113">The implementation relies on IntegerSquare.</span></span>