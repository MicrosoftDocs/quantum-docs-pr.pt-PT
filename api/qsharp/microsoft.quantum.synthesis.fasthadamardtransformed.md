---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Função FastHadamardTransformed
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203098"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="cb346-102">Função FastHadamardTransformed</span><span class="sxs-lookup"><span data-stu-id="cb346-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="cb346-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cb346-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cb346-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb346-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb346-105">Computes Hadamard transformar uma função Boolean na {-1,1} codificação usando o método de Yates</span><span class="sxs-lookup"><span data-stu-id="cb346-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="cb346-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cb346-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="cb346-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cb346-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cb346-108">Tabela da verdade na {-1,1} codificação</span><span class="sxs-lookup"><span data-stu-id="cb346-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="cb346-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cb346-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cb346-110">Coeficientes espectrais da função</span><span class="sxs-lookup"><span data-stu-id="cb346-110">Spectral coefficients of the function</span></span>