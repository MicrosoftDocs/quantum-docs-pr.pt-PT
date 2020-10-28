---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Função SquaredNorm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725021"
---
# <a name="squarednorm-function"></a><span data-ttu-id="50885-102">Função SquaredNorm</span><span class="sxs-lookup"><span data-stu-id="50885-102">SquaredNorm function</span></span>

<span data-ttu-id="50885-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="50885-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="50885-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50885-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50885-105">Devolve a norma quadrada de 2 de um vetor.</span><span class="sxs-lookup"><span data-stu-id="50885-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="50885-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="50885-106">Description</span></span>

<span data-ttu-id="50885-107">Devolve a 2-norma quadrada de um vetor; ou seja, dada uma entrada $\vec{x}$, devolve $\sum_i x_i^2$.</span><span class="sxs-lookup"><span data-stu-id="50885-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="50885-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="50885-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="50885-109">matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="50885-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="50885-110">O vetor cujo quadrado 2-norma é para ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="50885-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="50885-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50885-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50885-112">A norma de 2 000 quadrados de `array` .</span><span class="sxs-lookup"><span data-stu-id="50885-112">The squared 2-norm of `array`.</span></span>