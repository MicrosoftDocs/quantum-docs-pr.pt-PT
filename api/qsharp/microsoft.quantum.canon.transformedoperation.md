---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: Função de Cooperação Transformada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715340"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="e3f3a-102">Função de Cooperação Transformada</span><span class="sxs-lookup"><span data-stu-id="e3f3a-102">TransformedOperation function</span></span>

<span data-ttu-id="e3f3a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e3f3a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e3f3a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3f3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3f3a-105">Dada a função e uma operação, devolve uma nova operação cuja entrada é transformada pela função dada.</span><span class="sxs-lookup"><span data-stu-id="e3f3a-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="e3f3a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e3f3a-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="e3f3a-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="e3f3a-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="e3f3a-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="e3f3a-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="e3f3a-109">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e3f3a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e3f3a-110">A operação a ser transformada.</span><span class="sxs-lookup"><span data-stu-id="e3f3a-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="e3f3a-111">Saída : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e3f3a-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e3f3a-112">Uma nova operação de tbat chama `fn` com a sua entrada e, em seguida, passa a saída resultante para `op` .</span><span class="sxs-lookup"><span data-stu-id="e3f3a-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e3f3a-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e3f3a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e3f3a-114">'T</span><span class="sxs-lookup"><span data-stu-id="e3f3a-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="e3f3a-115">'U</span><span class="sxs-lookup"><span data-stu-id="e3f3a-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="e3f3a-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e3f3a-116">See Also</span></span>

- [<span data-ttu-id="e3f3a-117">Microsoft.Quantum.Canon.TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="e3f3a-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="e3f3a-118">Microsoft.Quantum.Canon.TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="e3f3a-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="e3f3a-119">Microsoft.Quantum.Canon.TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="e3f3a-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="e3f3a-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="e3f3a-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="e3f3a-121">Microsoft.Quantum.Canon.Composed</span><span class="sxs-lookup"><span data-stu-id="e3f3a-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)