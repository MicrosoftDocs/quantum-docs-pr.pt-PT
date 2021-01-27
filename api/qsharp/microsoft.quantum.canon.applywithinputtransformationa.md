---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Aplicação ComInputTransformationA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841130"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="03234-102">Aplicação ComInputTransformationA operação</span><span class="sxs-lookup"><span data-stu-id="03234-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="03234-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="03234-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="03234-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03234-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03234-105">Dada uma operação que aceita alguma entrada, uma função que devolve uma saída compatível com essa operação, e uma entrada para essa função, aplica a operação utilizando a função para transformar a entrada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="03234-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="03234-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="03234-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="03234-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="03234-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="03234-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="03234-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="03234-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="03234-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="03234-110">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="03234-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="03234-111">entrada : 'U</span><span class="sxs-lookup"><span data-stu-id="03234-111">input : 'U</span></span>

<span data-ttu-id="03234-112">Uma entrada para a função.</span><span class="sxs-lookup"><span data-stu-id="03234-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="03234-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03234-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="03234-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="03234-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03234-115">'T</span><span class="sxs-lookup"><span data-stu-id="03234-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="03234-116">'U</span><span class="sxs-lookup"><span data-stu-id="03234-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="03234-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="03234-117">Example</span></span>

<span data-ttu-id="03234-118">A chamada a seguir @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" utiliza-se para aplicar uma operação concebida para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas numa entrada do @"Microsoft.Quantum.Arithmetic.LittleEndian" tipo:</span><span class="sxs-lookup"><span data-stu-id="03234-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="03234-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="03234-119">See Also</span></span>

- [<span data-ttu-id="03234-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="03234-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="03234-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="03234-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="03234-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="03234-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="03234-123">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="03234-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)