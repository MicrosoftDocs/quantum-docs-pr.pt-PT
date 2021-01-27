---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Função FastHadamardTransformed
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855457"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="c1474-102">Função FastHadamardTransformed</span><span class="sxs-lookup"><span data-stu-id="c1474-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="c1474-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c1474-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c1474-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1474-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1474-105">Computes Hadamard transformar uma função Boolean na {-1,1} codificação usando o método de Yates</span><span class="sxs-lookup"><span data-stu-id="c1474-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c1474-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1474-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="c1474-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c1474-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c1474-108">Tabela da verdade na {-1,1} codificação</span><span class="sxs-lookup"><span data-stu-id="c1474-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="c1474-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c1474-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c1474-110">Coeficientes espectrais da função</span><span class="sxs-lookup"><span data-stu-id="c1474-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="c1474-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c1474-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```