---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: Função TransformedOperationA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840149"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="65c56-102">Função TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="65c56-102">TransformedOperationA function</span></span>

<span data-ttu-id="65c56-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65c56-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65c56-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65c56-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65c56-105">Dada a função e uma operação, devolve uma nova operação cuja entrada é transformada pela função dada.</span><span class="sxs-lookup"><span data-stu-id="65c56-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="65c56-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="65c56-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="65c56-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="65c56-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="65c56-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="65c56-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="65c56-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="65c56-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="65c56-110">A operação a ser transformada.</span><span class="sxs-lookup"><span data-stu-id="65c56-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="65c56-111">Saída : 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="65c56-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="65c56-112">Uma nova operação de tbat chama `fn` com a sua entrada e, em seguida, passa a saída resultante para `op` .</span><span class="sxs-lookup"><span data-stu-id="65c56-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="65c56-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="65c56-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="65c56-114">'T</span><span class="sxs-lookup"><span data-stu-id="65c56-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="65c56-115">'U</span><span class="sxs-lookup"><span data-stu-id="65c56-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="65c56-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="65c56-116">Example</span></span>

<span data-ttu-id="65c56-117">A chamada a seguir @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" utiliza-se para transformar uma operação concebida para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas numa operação que aceita entradas do @"Microsoft.Quantum.Arithmetic.LittleEndian" tipo:</span><span class="sxs-lookup"><span data-stu-id="65c56-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="65c56-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="65c56-118">See Also</span></span>

- [<span data-ttu-id="65c56-119">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="65c56-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="65c56-120">Microsoft.Quantum.Canon.TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="65c56-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="65c56-121">Microsoft.Quantum.Canon.TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="65c56-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="65c56-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="65c56-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="65c56-123">Microsoft.Quantum.Canon.Composed</span><span class="sxs-lookup"><span data-stu-id="65c56-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)