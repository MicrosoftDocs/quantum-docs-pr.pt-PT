---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Aplicação ComInputTransformationC operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d877fedbc0caa1a9ebc87d80cbce9ab54ca20d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850360"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="a7266-102">Aplicação ComInputTransformationC operação</span><span class="sxs-lookup"><span data-stu-id="a7266-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="a7266-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a7266-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a7266-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7266-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7266-105">Dada uma operação que aceita alguma entrada, uma função que devolve uma saída compatível com essa operação, e uma entrada para essa função, aplica a operação utilizando a função para transformar a entrada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="a7266-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="a7266-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a7266-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="a7266-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="a7266-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="a7266-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="a7266-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="a7266-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="a7266-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a7266-110">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="a7266-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="a7266-111">entrada : 'U</span><span class="sxs-lookup"><span data-stu-id="a7266-111">input : 'U</span></span>

<span data-ttu-id="a7266-112">Uma entrada para a função.</span><span class="sxs-lookup"><span data-stu-id="a7266-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a7266-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7266-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a7266-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a7266-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7266-115">'T</span><span class="sxs-lookup"><span data-stu-id="a7266-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="a7266-116">'U</span><span class="sxs-lookup"><span data-stu-id="a7266-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="a7266-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a7266-117">Example</span></span>

<span data-ttu-id="a7266-118">A chamada a seguir @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" utiliza-se para aplicar uma operação concebida para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas numa entrada do @"Microsoft.Quantum.Arithmetic.LittleEndian" tipo:</span><span class="sxs-lookup"><span data-stu-id="a7266-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="a7266-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a7266-119">See Also</span></span>

- [<span data-ttu-id="a7266-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="a7266-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="a7266-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationa</span><span class="sxs-lookup"><span data-stu-id="a7266-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="a7266-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="a7266-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="a7266-123">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="a7266-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)