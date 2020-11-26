---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: Função LocalUnivariateMinimum
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: e804e6a6ed82f14dcc9b8f721ad503d77922dc0f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194088"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="c99dd-102">Função LocalUnivariateMinimum</span><span class="sxs-lookup"><span data-stu-id="c99dd-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="c99dd-103">Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="c99dd-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="c99dd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c99dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c99dd-105">Devolve o mínimo local para uma função univariada durante um intervalo limitado, utilizando uma busca de intervalo dourado.</span><span class="sxs-lookup"><span data-stu-id="c99dd-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="c99dd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c99dd-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="c99dd-107">fn : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c99dd-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c99dd-108">A função univariada a ser minimizada.</span><span class="sxs-lookup"><span data-stu-id="c99dd-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="c99dd-109">limites :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Duplo)](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c99dd-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="c99dd-110">O intervalo em que se encontra o mínimo local.</span><span class="sxs-lookup"><span data-stu-id="c99dd-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c99dd-111">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c99dd-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c99dd-112">A precisão na entrada da função a ser tolerada.</span><span class="sxs-lookup"><span data-stu-id="c99dd-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="c99dd-113">A procura por optima local continuará até que o intervalo seja menor em largura do que esta tolerância.</span><span class="sxs-lookup"><span data-stu-id="c99dd-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="c99dd-114">Saída : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="c99dd-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="c99dd-115">Um optima local da função dada, localizada dentro dos limites dados.</span><span class="sxs-lookup"><span data-stu-id="c99dd-115">A local optima of the given function, located within the given bounds.</span></span>