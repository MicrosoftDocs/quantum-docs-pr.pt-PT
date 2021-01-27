---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: Função TransformedOperationCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: bb39530ae28e17d07a6a5c2bb2d35f81be312d15
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840130"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="64d18-102">Função TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="64d18-102">TransformedOperationCA function</span></span>

<span data-ttu-id="64d18-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64d18-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64d18-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64d18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64d18-105">Dada a função e uma operação, devolve uma nova operação cuja entrada é transformada pela função dada.</span><span class="sxs-lookup"><span data-stu-id="64d18-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="64d18-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="64d18-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="64d18-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="64d18-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="64d18-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="64d18-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="64d18-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="64d18-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="64d18-110">A operação a ser transformada.</span><span class="sxs-lookup"><span data-stu-id="64d18-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj--ctl"></a><span data-ttu-id="64d18-111">Saída : 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="64d18-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="64d18-112">Uma nova operação de tbat chama `fn` com a sua entrada e, em seguida, passa a saída resultante para `op` .</span><span class="sxs-lookup"><span data-stu-id="64d18-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64d18-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="64d18-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64d18-114">'T</span><span class="sxs-lookup"><span data-stu-id="64d18-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="64d18-115">'U</span><span class="sxs-lookup"><span data-stu-id="64d18-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="64d18-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="64d18-116">Example</span></span>

<span data-ttu-id="64d18-117">A chamada a seguir @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" utiliza-se para transformar uma operação concebida para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas numa operação que aceita entradas do @"Microsoft.Quantum.Arithmetic.LittleEndian" tipo:</span><span class="sxs-lookup"><span data-stu-id="64d18-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="64d18-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="64d18-118">See Also</span></span>

- [<span data-ttu-id="64d18-119">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="64d18-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="64d18-120">Microsoft.Quantum.Canon.TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="64d18-120">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="64d18-121">Microsoft.Quantum.Canon.TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="64d18-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="64d18-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="64d18-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="64d18-123">Microsoft.Quantum.Canon.Composed</span><span class="sxs-lookup"><span data-stu-id="64d18-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)