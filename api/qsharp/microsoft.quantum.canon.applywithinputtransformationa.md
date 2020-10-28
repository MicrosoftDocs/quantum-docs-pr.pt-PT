---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Aplicação ComInputTransformationA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716852"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="5aad3-102">Aplicação ComInputTransformationA operação</span><span class="sxs-lookup"><span data-stu-id="5aad3-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="5aad3-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5aad3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5aad3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5aad3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5aad3-105">Dada uma operação que aceita alguma entrada, uma função que devolve uma saída compatível com essa operação, e uma entrada para essa função, aplica a operação utilizando a função para transformar a entrada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="5aad3-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="5aad3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5aad3-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="5aad3-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="5aad3-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="5aad3-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="5aad3-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="5aad3-109">op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj</span><span class="sxs-lookup"><span data-stu-id="5aad3-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="5aad3-110">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="5aad3-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="5aad3-111">entrada : 'U</span><span class="sxs-lookup"><span data-stu-id="5aad3-111">input : 'U</span></span>

<span data-ttu-id="5aad3-112">Uma entrada para a função.</span><span class="sxs-lookup"><span data-stu-id="5aad3-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5aad3-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5aad3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5aad3-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5aad3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5aad3-115">'T</span><span class="sxs-lookup"><span data-stu-id="5aad3-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="5aad3-116">'U</span><span class="sxs-lookup"><span data-stu-id="5aad3-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="5aad3-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5aad3-117">See Also</span></span>

- [<span data-ttu-id="5aad3-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="5aad3-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="5aad3-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="5aad3-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="5aad3-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="5aad3-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="5aad3-121">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="5aad3-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)