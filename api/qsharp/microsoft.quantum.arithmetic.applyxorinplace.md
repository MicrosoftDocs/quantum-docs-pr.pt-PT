---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operação ApplyXorInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721391"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="48594-102">Operação ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="48594-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="48594-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="48594-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="48594-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48594-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48594-105">Aplica uma operação pouco-XOR entre um inteiro clássico e um inteiro representado por um registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="48594-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="48594-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="48594-106">Description</span></span>

<span data-ttu-id="48594-107">Aplica `X` operações a qubits num registo de pequenas extremidades com base em 1 bits num inteiro.</span><span class="sxs-lookup"><span data-stu-id="48594-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="48594-108">Vamos denotar `value` por um número inteiro não assinado codificado, em `target` seguida, executa uma `InPlaceXorLE` operação dada pelo seguinte mapa: $\ket{y}\rightarrow \ket{y\oplus a}, onde $\oplus$ é o operador exclusivo bitwise OR.</span><span class="sxs-lookup"><span data-stu-id="48594-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="48594-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="48594-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="48594-110">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="48594-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="48594-111">Um inteiro que se assume não negativo.</span><span class="sxs-lookup"><span data-stu-id="48594-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="48594-112">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="48594-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="48594-113">Um registo quântico que é usado para armazenar `value` em codificação pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="48594-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48594-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48594-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

