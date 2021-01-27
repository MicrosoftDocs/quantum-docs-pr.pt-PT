---
uid: Microsoft.Quantum.Math.SquaredNorm
title: Função SquaredNorm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848222"
---
# <a name="squarednorm-function"></a><span data-ttu-id="32e36-102">Função SquaredNorm</span><span class="sxs-lookup"><span data-stu-id="32e36-102">SquaredNorm function</span></span>

<span data-ttu-id="32e36-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="32e36-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="32e36-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32e36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32e36-105">Devolve a norma quadrada de 2 de um vetor.</span><span class="sxs-lookup"><span data-stu-id="32e36-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="32e36-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="32e36-106">Description</span></span>

<span data-ttu-id="32e36-107">Devolve a 2-norma quadrada de um vetor; ou seja, dada uma entrada $\vec{x}$, devolve $\sum_i x_i^2$.</span><span class="sxs-lookup"><span data-stu-id="32e36-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="32e36-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="32e36-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="32e36-109">matriz : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="32e36-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="32e36-110">O vetor cujo quadrado 2-norma é para ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="32e36-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="32e36-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="32e36-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="32e36-112">A norma de 2 000 quadrados de `array` .</span><span class="sxs-lookup"><span data-stu-id="32e36-112">The squared 2-norm of `array`.</span></span>