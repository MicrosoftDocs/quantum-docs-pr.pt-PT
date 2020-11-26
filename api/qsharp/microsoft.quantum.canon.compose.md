---
uid: Microsoft.Quantum.Canon.Compose
title: Função de composição
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216766"
---
# <a name="compose-function"></a><span data-ttu-id="9fe03-102">Função de composição</span><span class="sxs-lookup"><span data-stu-id="9fe03-102">Compose function</span></span>

<span data-ttu-id="9fe03-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9fe03-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9fe03-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fe03-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fe03-105">Devolve a composição de duas funções.</span><span class="sxs-lookup"><span data-stu-id="9fe03-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="9fe03-106">Description</span><span class="sxs-lookup"><span data-stu-id="9fe03-106">Description</span></span>

<span data-ttu-id="9fe03-107">Tendo em conta duas funções $f$ e $g$, devolve uma nova função que representa $f \circ g$.</span><span class="sxs-lookup"><span data-stu-id="9fe03-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="9fe03-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="9fe03-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="9fe03-109">exterior : 'U -> 'V</span><span class="sxs-lookup"><span data-stu-id="9fe03-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="9fe03-110">A segunda função a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="9fe03-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="9fe03-111">interior : 'T-> 'U</span><span class="sxs-lookup"><span data-stu-id="9fe03-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="9fe03-112">A primeira função a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="9fe03-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="9fe03-113">Saída : 'T-> 'V</span><span class="sxs-lookup"><span data-stu-id="9fe03-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="9fe03-114">Uma nova função $h$ tal que para todas as entradas $x$, $f(g(x)= h(x)$.</span><span class="sxs-lookup"><span data-stu-id="9fe03-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9fe03-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9fe03-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9fe03-116">'T</span><span class="sxs-lookup"><span data-stu-id="9fe03-116">'T</span></span>

<span data-ttu-id="9fe03-117">O tipo de entrada da primeira função a aplicar.</span><span class="sxs-lookup"><span data-stu-id="9fe03-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="9fe03-118">'U</span><span class="sxs-lookup"><span data-stu-id="9fe03-118">'U</span></span>

<span data-ttu-id="9fe03-119">O tipo de saída da primeira função a aplicar e o tipo de entrada da segunda função a aplicar.</span><span class="sxs-lookup"><span data-stu-id="9fe03-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="9fe03-120">'V</span><span class="sxs-lookup"><span data-stu-id="9fe03-120">'V</span></span>

<span data-ttu-id="9fe03-121">O tipo de saída da segunda função a aplicar.</span><span class="sxs-lookup"><span data-stu-id="9fe03-121">The output type of the second function to be applied.</span></span>