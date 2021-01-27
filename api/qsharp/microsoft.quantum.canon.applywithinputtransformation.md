---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Aplicação ComInputTransformação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850380"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="2e1c9-102">Aplicação ComInputTransformação</span><span class="sxs-lookup"><span data-stu-id="2e1c9-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="2e1c9-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e1c9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e1c9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e1c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e1c9-105">Dada uma operação que aceita alguma entrada, uma função que devolve uma saída compatível com essa operação, e uma entrada para essa função, aplica a operação utilizando a função para transformar a entrada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="2e1c9-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="2e1c9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e1c9-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="2e1c9-107">fn : 'U -> 'T</span><span class="sxs-lookup"><span data-stu-id="2e1c9-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="2e1c9-108">Uma função que transforma a entrada dada num formulário esperado pela operação.</span><span class="sxs-lookup"><span data-stu-id="2e1c9-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="2e1c9-109">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="2e1c9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2e1c9-110">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="2e1c9-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="2e1c9-111">entrada : 'U</span><span class="sxs-lookup"><span data-stu-id="2e1c9-111">input : 'U</span></span>

<span data-ttu-id="2e1c9-112">Uma entrada para a função.</span><span class="sxs-lookup"><span data-stu-id="2e1c9-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e1c9-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e1c9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2e1c9-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2e1c9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e1c9-115">'T</span><span class="sxs-lookup"><span data-stu-id="2e1c9-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="2e1c9-116">'U</span><span class="sxs-lookup"><span data-stu-id="2e1c9-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="2e1c9-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2e1c9-117">Example</span></span>

<span data-ttu-id="2e1c9-118">A chamada a seguir @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" utiliza-se para aplicar uma operação concebida para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas numa entrada do @"Microsoft.Quantum.Arithmetic.LittleEndian" tipo:</span><span class="sxs-lookup"><span data-stu-id="2e1c9-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="2e1c9-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2e1c9-119">See Also</span></span>

- [<span data-ttu-id="2e1c9-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationa</span><span class="sxs-lookup"><span data-stu-id="2e1c9-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="2e1c9-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="2e1c9-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="2e1c9-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="2e1c9-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="2e1c9-123">Microsoft.Quantum.Canon.TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="2e1c9-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)