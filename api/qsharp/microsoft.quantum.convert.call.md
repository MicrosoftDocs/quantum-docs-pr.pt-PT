---
uid: Microsoft.Quantum.Convert.Call
title: Operação de chamada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214216"
---
# <a name="call-operation"></a><span data-ttu-id="67dbe-102">Operação de chamada</span><span class="sxs-lookup"><span data-stu-id="67dbe-102">Call operation</span></span>

<span data-ttu-id="67dbe-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="67dbe-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="67dbe-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67dbe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67dbe-105">Chama uma função com uma dada entrada.</span><span class="sxs-lookup"><span data-stu-id="67dbe-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="67dbe-106">Description</span><span class="sxs-lookup"><span data-stu-id="67dbe-106">Description</span></span>

<span data-ttu-id="67dbe-107">Dada uma função e uma entrada para essa função, chama a função e devolve a sua saída.</span><span class="sxs-lookup"><span data-stu-id="67dbe-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="67dbe-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="67dbe-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="67dbe-109">fn : 'Entrada -> 'Saída</span><span class="sxs-lookup"><span data-stu-id="67dbe-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="67dbe-110">Uma função a ser chamada.</span><span class="sxs-lookup"><span data-stu-id="67dbe-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="67dbe-111">entrada : 'Entrada</span><span class="sxs-lookup"><span data-stu-id="67dbe-111">input : 'Input</span></span>

<span data-ttu-id="67dbe-112">A entrada a ser passada para a função.</span><span class="sxs-lookup"><span data-stu-id="67dbe-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="67dbe-113">Saída : 'Saída</span><span class="sxs-lookup"><span data-stu-id="67dbe-113">Output : 'Output</span></span>

<span data-ttu-id="67dbe-114">O resultado da `fn` chamada.</span><span class="sxs-lookup"><span data-stu-id="67dbe-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="67dbe-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="67dbe-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="67dbe-116">'Entrada</span><span class="sxs-lookup"><span data-stu-id="67dbe-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="67dbe-117">'Saída</span><span class="sxs-lookup"><span data-stu-id="67dbe-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="67dbe-118">Observações</span><span class="sxs-lookup"><span data-stu-id="67dbe-118">Remarks</span></span>

<span data-ttu-id="67dbe-119">Esta operação é principalmente útil para forçar uma função a ser chamada num local específico dentro de uma operação, ou para chamar uma função onde uma operação é esperada.</span><span class="sxs-lookup"><span data-stu-id="67dbe-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>