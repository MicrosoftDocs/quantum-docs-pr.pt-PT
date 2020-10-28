---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Aplicação ComInputTransformationCA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c80ce0887a202a60de81c2d12fa95ce1eab59058
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716838"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="d7e9b-102">Aplicação ComInputTransformationCA operação</span><span class="sxs-lookup"><span data-stu-id="d7e9b-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="d7e9b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7e9b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7e9b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7e9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7e9b-105">Dada uma operação que aceita alguma entrada, uma função que devolve uma saída compatível com essa operação, e uma entrada para essa função, aplica a operação utilizando a função para transformar a entrada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="d7e9b-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="d7e9b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d7e9b-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="d7e9b-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="d7e9b-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="d7e9b-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="d7e9b-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="d7e9b-109">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="d7e9b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d7e9b-110">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="d7e9b-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="d7e9b-111">entrada : 'U</span><span class="sxs-lookup"><span data-stu-id="d7e9b-111">input : 'U</span></span>

<span data-ttu-id="d7e9b-112">Uma entrada para a função.</span><span class="sxs-lookup"><span data-stu-id="d7e9b-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7e9b-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7e9b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d7e9b-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d7e9b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7e9b-115">'T</span><span class="sxs-lookup"><span data-stu-id="d7e9b-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="d7e9b-116">'U</span><span class="sxs-lookup"><span data-stu-id="d7e9b-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="d7e9b-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d7e9b-117">See Also</span></span>

- [<span data-ttu-id="d7e9b-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="d7e9b-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="d7e9b-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationa</span><span class="sxs-lookup"><span data-stu-id="d7e9b-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="d7e9b-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="d7e9b-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="d7e9b-121">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="d7e9b-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)