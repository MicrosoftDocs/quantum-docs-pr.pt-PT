---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Aplicação ComInputTransformationCA operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207790"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="159f5-102">Aplicação ComInputTransformationCA operação</span><span class="sxs-lookup"><span data-stu-id="159f5-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="159f5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="159f5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="159f5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="159f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="159f5-105">Dada uma operação que aceita alguma entrada, uma função que devolve uma saída compatível com essa operação, e uma entrada para essa função, aplica a operação utilizando a função para transformar a entrada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="159f5-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="159f5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="159f5-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="159f5-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="159f5-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="159f5-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="159f5-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="159f5-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="159f5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="159f5-110">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="159f5-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="159f5-111">entrada : 'U</span><span class="sxs-lookup"><span data-stu-id="159f5-111">input : 'U</span></span>

<span data-ttu-id="159f5-112">Uma entrada para a função.</span><span class="sxs-lookup"><span data-stu-id="159f5-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="159f5-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="159f5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="159f5-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="159f5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="159f5-115">'T</span><span class="sxs-lookup"><span data-stu-id="159f5-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="159f5-116">'U</span><span class="sxs-lookup"><span data-stu-id="159f5-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="159f5-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="159f5-117">See Also</span></span>

- [<span data-ttu-id="159f5-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="159f5-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="159f5-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationa</span><span class="sxs-lookup"><span data-stu-id="159f5-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="159f5-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="159f5-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="159f5-121">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="159f5-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)