---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunçãoAsOperação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713509"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="3979b-102">FunçãoAsOperação</span><span class="sxs-lookup"><span data-stu-id="3979b-102">FunctionAsOperation function</span></span>

<span data-ttu-id="3979b-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="3979b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="3979b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3979b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3979b-105">Converte funções em operações.</span><span class="sxs-lookup"><span data-stu-id="3979b-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="3979b-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="3979b-106">Description</span></span>

<span data-ttu-id="3979b-107">Dada uma função, retorna uma operação que chama a essa função, e que não faz mais nada.</span><span class="sxs-lookup"><span data-stu-id="3979b-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="3979b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3979b-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="3979b-109">fn : 'Entrada -> 'Saída</span><span class="sxs-lookup"><span data-stu-id="3979b-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="3979b-110">Uma função a converter para uma operação.</span><span class="sxs-lookup"><span data-stu-id="3979b-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="3979b-111">Saída : 'Entrada => 'Saída</span><span class="sxs-lookup"><span data-stu-id="3979b-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="3979b-112">Uma operação `op` idêntica `op(input)` a `fn(input)` `input` todas.</span><span class="sxs-lookup"><span data-stu-id="3979b-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3979b-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="3979b-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="3979b-114">'Entrada</span><span class="sxs-lookup"><span data-stu-id="3979b-114">'Input</span></span>

<span data-ttu-id="3979b-115">Tipo de entrada da função a converter.</span><span class="sxs-lookup"><span data-stu-id="3979b-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="3979b-116">'Saída</span><span class="sxs-lookup"><span data-stu-id="3979b-116">'Output</span></span>

<span data-ttu-id="3979b-117">Tipo de saída da função a converter.</span><span class="sxs-lookup"><span data-stu-id="3979b-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="3979b-118">Observações</span><span class="sxs-lookup"><span data-stu-id="3979b-118">Remarks</span></span>

<span data-ttu-id="3979b-119">Isto é principalmente útil para passar funções para funções ou operações que esperam uma operação como entrada.</span><span class="sxs-lookup"><span data-stu-id="3979b-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>