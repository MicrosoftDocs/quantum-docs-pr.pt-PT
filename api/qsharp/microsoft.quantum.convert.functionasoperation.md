---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunçãoAsOperação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833829"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="e6021-102">FunçãoAsOperação</span><span class="sxs-lookup"><span data-stu-id="e6021-102">FunctionAsOperation function</span></span>

<span data-ttu-id="e6021-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e6021-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e6021-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6021-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6021-105">Converte funções em operações.</span><span class="sxs-lookup"><span data-stu-id="e6021-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="e6021-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6021-106">Description</span></span>

<span data-ttu-id="e6021-107">Dada uma função, retorna uma operação que chama a essa função, e que não faz mais nada.</span><span class="sxs-lookup"><span data-stu-id="e6021-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="e6021-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e6021-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="e6021-109">fn : 'Entrada -> 'Saída</span><span class="sxs-lookup"><span data-stu-id="e6021-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="e6021-110">Uma função a converter para uma operação.</span><span class="sxs-lookup"><span data-stu-id="e6021-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="e6021-111">Saída : 'Entrada => 'Saída</span><span class="sxs-lookup"><span data-stu-id="e6021-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="e6021-112">Uma operação `op` idêntica `op(input)` a `fn(input)` `input` todas.</span><span class="sxs-lookup"><span data-stu-id="e6021-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e6021-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e6021-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="e6021-114">'Entrada</span><span class="sxs-lookup"><span data-stu-id="e6021-114">'Input</span></span>

<span data-ttu-id="e6021-115">Tipo de entrada da função a converter.</span><span class="sxs-lookup"><span data-stu-id="e6021-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="e6021-116">'Saída</span><span class="sxs-lookup"><span data-stu-id="e6021-116">'Output</span></span>

<span data-ttu-id="e6021-117">Tipo de saída da função a converter.</span><span class="sxs-lookup"><span data-stu-id="e6021-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6021-118">Observações</span><span class="sxs-lookup"><span data-stu-id="e6021-118">Remarks</span></span>

<span data-ttu-id="e6021-119">Isto é principalmente útil para passar funções para funções ou operações que esperam uma operação como entrada.</span><span class="sxs-lookup"><span data-stu-id="e6021-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>