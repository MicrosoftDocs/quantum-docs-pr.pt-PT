---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operação ApplyXorInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843479"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="45a8c-102">Operação ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="45a8c-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="45a8c-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="45a8c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="45a8c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45a8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45a8c-105">Aplica uma operação pouco-XOR entre um inteiro clássico e um inteiro representado por um registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="45a8c-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="45a8c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="45a8c-106">Description</span></span>

<span data-ttu-id="45a8c-107">Aplica `X` operações a qubits num registo de pequenas extremidades com base em 1 bits num inteiro.</span><span class="sxs-lookup"><span data-stu-id="45a8c-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="45a8c-108">Vamos denotar `value` por um número inteiro não assinado codificado, em `target` seguida, executa uma `InPlaceXorLE` operação dada pelo seguinte mapa: $\ket{y}\rightarrow \ket{y\oplus a}, onde $\oplus$ é o operador exclusivo bitwise OR.</span><span class="sxs-lookup"><span data-stu-id="45a8c-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="45a8c-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="45a8c-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="45a8c-110">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45a8c-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="45a8c-111">Um inteiro que se assume não negativo.</span><span class="sxs-lookup"><span data-stu-id="45a8c-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="45a8c-112">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45a8c-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45a8c-113">Um registo quântico que é usado para armazenar `value` em codificação pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="45a8c-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45a8c-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45a8c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

