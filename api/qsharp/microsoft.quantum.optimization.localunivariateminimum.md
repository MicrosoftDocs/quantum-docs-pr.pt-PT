---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: Função LocalUnivariateMinimum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711017"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="ba5db-102">Função LocalUnivariateMinimum</span><span class="sxs-lookup"><span data-stu-id="ba5db-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="ba5db-103">Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="ba5db-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="ba5db-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba5db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba5db-105">Devolve o mínimo local para uma função univariada durante um intervalo limitado, utilizando uma busca de intervalo dourado.</span><span class="sxs-lookup"><span data-stu-id="ba5db-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="ba5db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ba5db-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="ba5db-107">fn : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ba5db-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ba5db-108">A função univariada a ser minimizada.</span><span class="sxs-lookup"><span data-stu-id="ba5db-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="ba5db-109">limites :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Duplo)](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ba5db-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="ba5db-110">O intervalo em que se encontra o mínimo local.</span><span class="sxs-lookup"><span data-stu-id="ba5db-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ba5db-111">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ba5db-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ba5db-112">A precisão na entrada da função a ser tolerada.</span><span class="sxs-lookup"><span data-stu-id="ba5db-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="ba5db-113">A procura por optima local continuará até que o intervalo seja menor em largura do que esta tolerância.</span><span class="sxs-lookup"><span data-stu-id="ba5db-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="ba5db-114">Saída : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="ba5db-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="ba5db-115">Um optima local da função dada, localizada dentro dos limites dados.</span><span class="sxs-lookup"><span data-stu-id="ba5db-115">A local optima of the given function, located within the given bounds.</span></span>