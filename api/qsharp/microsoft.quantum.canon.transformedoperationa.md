---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: Função TransformedOperationA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: eceba260e601b73bdfa2de6ea6ab146820b5c59a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204883"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="76681-102">Função TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="76681-102">TransformedOperationA function</span></span>

<span data-ttu-id="76681-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76681-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76681-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76681-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76681-105">Dada a função e uma operação, devolve uma nova operação cuja entrada é transformada pela função dada.</span><span class="sxs-lookup"><span data-stu-id="76681-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="76681-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="76681-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="76681-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="76681-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="76681-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="76681-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="76681-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="76681-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="76681-110">A operação a ser transformada.</span><span class="sxs-lookup"><span data-stu-id="76681-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="76681-111">Saída : 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="76681-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="76681-112">Uma nova operação de tbat chama `fn` com a sua entrada e, em seguida, passa a saída resultante para `op` .</span><span class="sxs-lookup"><span data-stu-id="76681-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="76681-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="76681-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76681-114">'T</span><span class="sxs-lookup"><span data-stu-id="76681-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="76681-115">'U</span><span class="sxs-lookup"><span data-stu-id="76681-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="76681-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="76681-116">See Also</span></span>

- [<span data-ttu-id="76681-117">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="76681-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="76681-118">Microsoft.Quantum.Canon.TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="76681-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="76681-119">Microsoft.Quantum.Canon.TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="76681-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="76681-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="76681-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="76681-121">Microsoft.Quantum.Canon.Composed</span><span class="sxs-lookup"><span data-stu-id="76681-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)