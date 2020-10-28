---
uid: Microsoft.Quantum.Math.PlusA
title: Função PlusA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709603"
---
# <a name="plusa-function"></a><span data-ttu-id="9fc99-102">Função PlusA</span><span class="sxs-lookup"><span data-stu-id="9fc99-102">PlusA function</span></span>

<span data-ttu-id="9fc99-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9fc99-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9fc99-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fc99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fc99-105">Devolve a soma (concatenação) de duas entradas.</span><span class="sxs-lookup"><span data-stu-id="9fc99-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="9fc99-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9fc99-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="9fc99-107">a : «Elemento].</span><span class="sxs-lookup"><span data-stu-id="9fc99-107">a : 'Element[]</span></span>

<span data-ttu-id="9fc99-108">A primeira entrada $a$ a ser resumida.</span><span class="sxs-lookup"><span data-stu-id="9fc99-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="9fc99-109">b : «Elemento].</span><span class="sxs-lookup"><span data-stu-id="9fc99-109">b : 'Element[]</span></span>

<span data-ttu-id="9fc99-110">A segunda entrada $b$ a resumir.</span><span class="sxs-lookup"><span data-stu-id="9fc99-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="9fc99-111">Saída : «Elemento[]</span><span class="sxs-lookup"><span data-stu-id="9fc99-111">Output : 'Element[]</span></span>

<span data-ttu-id="9fc99-112">A soma $a + b$.</span><span class="sxs-lookup"><span data-stu-id="9fc99-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9fc99-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9fc99-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="9fc99-114">'Elemento</span><span class="sxs-lookup"><span data-stu-id="9fc99-114">'Element</span></span>

<span data-ttu-id="9fc99-115">O tipo de cada elemento em cada uma das duas matrizes de entrada.</span><span class="sxs-lookup"><span data-stu-id="9fc99-115">The type of each element in each of the two input arrays.</span></span>