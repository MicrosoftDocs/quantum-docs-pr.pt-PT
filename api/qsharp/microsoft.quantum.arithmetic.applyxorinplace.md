---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operação ApplyXorInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210118"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="cba58-102">Operação ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="cba58-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="cba58-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cba58-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cba58-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cba58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cba58-105">Aplica uma operação pouco-XOR entre um inteiro clássico e um inteiro representado por um registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="cba58-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cba58-106">Description</span><span class="sxs-lookup"><span data-stu-id="cba58-106">Description</span></span>

<span data-ttu-id="cba58-107">Aplica `X` operações a qubits num registo de pequenas extremidades com base em 1 bits num inteiro.</span><span class="sxs-lookup"><span data-stu-id="cba58-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="cba58-108">Vamos denotar `value` por um número inteiro não assinado codificado, em `target` seguida, executa uma `InPlaceXorLE` operação dada pelo seguinte mapa: $\ket{y}\rightarrow \ket{y\oplus a}, onde $\oplus$ é o operador exclusivo bitwise OR.</span><span class="sxs-lookup"><span data-stu-id="cba58-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="cba58-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="cba58-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="cba58-110">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cba58-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cba58-111">Um inteiro que se assume não negativo.</span><span class="sxs-lookup"><span data-stu-id="cba58-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="cba58-112">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cba58-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cba58-113">Um registo quântico que é usado para armazenar `value` em codificação pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="cba58-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cba58-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cba58-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

