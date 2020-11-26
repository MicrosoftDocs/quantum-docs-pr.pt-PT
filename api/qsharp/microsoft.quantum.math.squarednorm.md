---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Função SquaredNorm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227306"
---
# <a name="squarednorm-function"></a><span data-ttu-id="ffb4d-102">Função SquaredNorm</span><span class="sxs-lookup"><span data-stu-id="ffb4d-102">SquaredNorm function</span></span>

<span data-ttu-id="ffb4d-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ffb4d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ffb4d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffb4d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffb4d-105">Devolve a norma quadrada de 2 de um vetor.</span><span class="sxs-lookup"><span data-stu-id="ffb4d-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="ffb4d-106">Description</span><span class="sxs-lookup"><span data-stu-id="ffb4d-106">Description</span></span>

<span data-ttu-id="ffb4d-107">Devolve a 2-norma quadrada de um vetor; ou seja, dada uma entrada $\vec{x}$, devolve $\sum_i x_i^2$.</span><span class="sxs-lookup"><span data-stu-id="ffb4d-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="ffb4d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ffb4d-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="ffb4d-109">matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ffb4d-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ffb4d-110">O vetor cujo quadrado 2-norma é para ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="ffb4d-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="ffb4d-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ffb4d-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ffb4d-112">A norma de 2 000 quadrados de `array` .</span><span class="sxs-lookup"><span data-stu-id="ffb4d-112">The squared 2-norm of `array`.</span></span>