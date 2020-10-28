---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Operação MultiplySI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719747"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="64beb-102">Operação MultiplySI</span><span class="sxs-lookup"><span data-stu-id="64beb-102">MultiplySI operation</span></span>

<span data-ttu-id="64beb-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="64beb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="64beb-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64beb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64beb-105">Multiplique o inteiro assinado `xs` por inteiro assinado e `ys` guarde o resultado em , que deve `result` ser zero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="64beb-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="64beb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="64beb-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="64beb-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="64beb-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="64beb-108">multiplicand n bit (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="64beb-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="64beb-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="64beb-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="64beb-110">multiplicador n bit (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="64beb-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="64beb-111">resultado : [AssinadoLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="64beb-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="64beb-112">Resultado de 2n-bit (SignedLittleEndian), deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="64beb-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64beb-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64beb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

