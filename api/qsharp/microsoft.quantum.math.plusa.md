---
uid: Microsoft.Quantum.Math.PlusA
title: Função PlusA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194836"
---
# <a name="plusa-function"></a><span data-ttu-id="46470-102">Função PlusA</span><span class="sxs-lookup"><span data-stu-id="46470-102">PlusA function</span></span>

<span data-ttu-id="46470-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="46470-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="46470-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46470-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46470-105">Devolve a soma (concatenação) de duas entradas.</span><span class="sxs-lookup"><span data-stu-id="46470-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="46470-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="46470-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="46470-107">a : «Elemento].</span><span class="sxs-lookup"><span data-stu-id="46470-107">a : 'Element[]</span></span>

<span data-ttu-id="46470-108">A primeira entrada $a$ a ser resumida.</span><span class="sxs-lookup"><span data-stu-id="46470-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="46470-109">b : «Elemento].</span><span class="sxs-lookup"><span data-stu-id="46470-109">b : 'Element[]</span></span>

<span data-ttu-id="46470-110">A segunda entrada $b$ a resumir.</span><span class="sxs-lookup"><span data-stu-id="46470-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="46470-111">Saída : «Elemento[]</span><span class="sxs-lookup"><span data-stu-id="46470-111">Output : 'Element[]</span></span>

<span data-ttu-id="46470-112">A soma $a + b$.</span><span class="sxs-lookup"><span data-stu-id="46470-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="46470-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="46470-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="46470-114">'Elemento</span><span class="sxs-lookup"><span data-stu-id="46470-114">'Element</span></span>

<span data-ttu-id="46470-115">O tipo de cada elemento em cada uma das duas matrizes de entrada.</span><span class="sxs-lookup"><span data-stu-id="46470-115">The type of each element in each of the two input arrays.</span></span>