---
uid: Microsoft.Quantum.Canon.Compose
title: Função de composição
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840912"
---
# <a name="compose-function"></a><span data-ttu-id="f0533-102">Função de composição</span><span class="sxs-lookup"><span data-stu-id="f0533-102">Compose function</span></span>

<span data-ttu-id="f0533-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f0533-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f0533-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0533-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0533-105">Devolve a composição de duas funções.</span><span class="sxs-lookup"><span data-stu-id="f0533-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="f0533-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0533-106">Description</span></span>

<span data-ttu-id="f0533-107">Tendo em conta duas funções $f$ e $g$, devolve uma nova função que representa $f \circ g$.</span><span class="sxs-lookup"><span data-stu-id="f0533-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="f0533-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f0533-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="f0533-109">exterior : 'U -> 'V</span><span class="sxs-lookup"><span data-stu-id="f0533-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="f0533-110">A segunda função a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f0533-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="f0533-111">interior : 'T-> 'U</span><span class="sxs-lookup"><span data-stu-id="f0533-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="f0533-112">A primeira função a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f0533-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="f0533-113">Saída : 'T-> 'V</span><span class="sxs-lookup"><span data-stu-id="f0533-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="f0533-114">Uma nova função $h$ tal que para todas as entradas $x$, $f(g(x)= h(x)$.</span><span class="sxs-lookup"><span data-stu-id="f0533-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0533-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f0533-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f0533-116">'T</span><span class="sxs-lookup"><span data-stu-id="f0533-116">'T</span></span>

<span data-ttu-id="f0533-117">O tipo de entrada da primeira função a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f0533-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="f0533-118">'U</span><span class="sxs-lookup"><span data-stu-id="f0533-118">'U</span></span>

<span data-ttu-id="f0533-119">O tipo de saída da primeira função a aplicar e o tipo de entrada da segunda função a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f0533-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="f0533-120">'V</span><span class="sxs-lookup"><span data-stu-id="f0533-120">'V</span></span>

<span data-ttu-id="f0533-121">O tipo de saída da segunda função a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f0533-121">The output type of the second function to be applied.</span></span>