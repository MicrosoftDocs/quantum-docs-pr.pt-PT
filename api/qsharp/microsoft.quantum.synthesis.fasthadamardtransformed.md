---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Função FastHadamardTransformed
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725186"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="99596-102">Função FastHadamardTransformed</span><span class="sxs-lookup"><span data-stu-id="99596-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="99596-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="99596-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="99596-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99596-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99596-105">Computes Hadamard transformar uma função Boolean na {-1,1} codificação usando o método de Yates</span><span class="sxs-lookup"><span data-stu-id="99596-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="99596-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="99596-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="99596-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="99596-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="99596-108">Tabela da verdade na {-1,1} codificação</span><span class="sxs-lookup"><span data-stu-id="99596-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="99596-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="99596-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="99596-110">Coeficientes espectrais da função</span><span class="sxs-lookup"><span data-stu-id="99596-110">Spectral coefficients of the function</span></span>