---
uid: Microsoft.Quantum.Math.PlusA
title: Função PlusA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842707"
---
# <a name="plusa-function"></a><span data-ttu-id="60b59-102">Função PlusA</span><span class="sxs-lookup"><span data-stu-id="60b59-102">PlusA function</span></span>

<span data-ttu-id="60b59-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="60b59-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="60b59-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60b59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60b59-105">Devolve a soma (concatenação) de duas entradas.</span><span class="sxs-lookup"><span data-stu-id="60b59-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="60b59-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="60b59-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="60b59-107">a : «Elemento].</span><span class="sxs-lookup"><span data-stu-id="60b59-107">a : 'Element[]</span></span>

<span data-ttu-id="60b59-108">A primeira entrada $a$ a ser resumida.</span><span class="sxs-lookup"><span data-stu-id="60b59-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="60b59-109">b : «Elemento].</span><span class="sxs-lookup"><span data-stu-id="60b59-109">b : 'Element[]</span></span>

<span data-ttu-id="60b59-110">A segunda entrada $b$ a resumir.</span><span class="sxs-lookup"><span data-stu-id="60b59-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="60b59-111">Saída : «Elemento[]</span><span class="sxs-lookup"><span data-stu-id="60b59-111">Output : 'Element[]</span></span>

<span data-ttu-id="60b59-112">A soma $a + b$.</span><span class="sxs-lookup"><span data-stu-id="60b59-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="60b59-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="60b59-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="60b59-114">'Elemento</span><span class="sxs-lookup"><span data-stu-id="60b59-114">'Element</span></span>

<span data-ttu-id="60b59-115">O tipo de cada elemento em cada uma das duas matrizes de entrada.</span><span class="sxs-lookup"><span data-stu-id="60b59-115">The type of each element in each of the two input arrays.</span></span>