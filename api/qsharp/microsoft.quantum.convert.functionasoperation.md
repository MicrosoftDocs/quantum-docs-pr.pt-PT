---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunçãoAsOperação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224382"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="7b092-102">FunçãoAsOperação</span><span class="sxs-lookup"><span data-stu-id="7b092-102">FunctionAsOperation function</span></span>

<span data-ttu-id="7b092-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="7b092-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="7b092-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b092-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b092-105">Converte funções em operações.</span><span class="sxs-lookup"><span data-stu-id="7b092-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="7b092-106">Description</span><span class="sxs-lookup"><span data-stu-id="7b092-106">Description</span></span>

<span data-ttu-id="7b092-107">Dada uma função, retorna uma operação que chama a essa função, e que não faz mais nada.</span><span class="sxs-lookup"><span data-stu-id="7b092-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="7b092-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7b092-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="7b092-109">fn : 'Entrada -> 'Saída</span><span class="sxs-lookup"><span data-stu-id="7b092-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="7b092-110">Uma função a converter para uma operação.</span><span class="sxs-lookup"><span data-stu-id="7b092-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="7b092-111">Saída : 'Entrada => 'Saída</span><span class="sxs-lookup"><span data-stu-id="7b092-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="7b092-112">Uma operação `op` idêntica `op(input)` a `fn(input)` `input` todas.</span><span class="sxs-lookup"><span data-stu-id="7b092-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7b092-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7b092-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="7b092-114">'Entrada</span><span class="sxs-lookup"><span data-stu-id="7b092-114">'Input</span></span>

<span data-ttu-id="7b092-115">Tipo de entrada da função a converter.</span><span class="sxs-lookup"><span data-stu-id="7b092-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="7b092-116">'Saída</span><span class="sxs-lookup"><span data-stu-id="7b092-116">'Output</span></span>

<span data-ttu-id="7b092-117">Tipo de saída da função a converter.</span><span class="sxs-lookup"><span data-stu-id="7b092-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b092-118">Observações</span><span class="sxs-lookup"><span data-stu-id="7b092-118">Remarks</span></span>

<span data-ttu-id="7b092-119">Isto é principalmente útil para passar funções para funções ou operações que esperam uma operação como entrada.</span><span class="sxs-lookup"><span data-stu-id="7b092-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>