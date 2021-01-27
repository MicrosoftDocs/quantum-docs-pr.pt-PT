---
uid: Microsoft.Quantum.Convert.Call
title: Operação de chamada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850202"
---
# <a name="call-operation"></a><span data-ttu-id="2080a-102">Operação de chamada</span><span class="sxs-lookup"><span data-stu-id="2080a-102">Call operation</span></span>

<span data-ttu-id="2080a-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="2080a-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="2080a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2080a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2080a-105">Chama uma função com uma dada entrada.</span><span class="sxs-lookup"><span data-stu-id="2080a-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="2080a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="2080a-106">Description</span></span>

<span data-ttu-id="2080a-107">Dada uma função e uma entrada para essa função, chama a função e devolve a sua saída.</span><span class="sxs-lookup"><span data-stu-id="2080a-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="2080a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2080a-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="2080a-109">fn : 'Entrada -> 'Saída</span><span class="sxs-lookup"><span data-stu-id="2080a-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="2080a-110">Uma função a ser chamada.</span><span class="sxs-lookup"><span data-stu-id="2080a-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="2080a-111">entrada : 'Entrada</span><span class="sxs-lookup"><span data-stu-id="2080a-111">input : 'Input</span></span>

<span data-ttu-id="2080a-112">A entrada a ser passada para a função.</span><span class="sxs-lookup"><span data-stu-id="2080a-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="2080a-113">Saída : 'Saída</span><span class="sxs-lookup"><span data-stu-id="2080a-113">Output : 'Output</span></span>

<span data-ttu-id="2080a-114">O resultado da `fn` chamada.</span><span class="sxs-lookup"><span data-stu-id="2080a-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2080a-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2080a-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="2080a-116">'Entrada</span><span class="sxs-lookup"><span data-stu-id="2080a-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="2080a-117">'Saída</span><span class="sxs-lookup"><span data-stu-id="2080a-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="2080a-118">Observações</span><span class="sxs-lookup"><span data-stu-id="2080a-118">Remarks</span></span>

<span data-ttu-id="2080a-119">Esta operação é principalmente útil para forçar uma função a ser chamada num local específico dentro de uma operação, ou para chamar uma função onde uma operação é esperada.</span><span class="sxs-lookup"><span data-stu-id="2080a-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>