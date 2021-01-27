---
uid: Microsoft.Quantum.Logical.Conditioned
title: Função condicionada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817293"
---
# <a name="conditioned-function"></a><span data-ttu-id="e5261-102">Função condicionada</span><span class="sxs-lookup"><span data-stu-id="e5261-102">Conditioned function</span></span>

<span data-ttu-id="e5261-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e5261-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e5261-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5261-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5261-105">Devolve um de dois valores, dependendo do valor de uma condição Booleana.</span><span class="sxs-lookup"><span data-stu-id="e5261-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="e5261-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e5261-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="e5261-107">condição : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e5261-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e5261-108">Uma condição usada para controlar a entrada que é devolvida.</span><span class="sxs-lookup"><span data-stu-id="e5261-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="e5261-109">ifTrue : 'T</span><span class="sxs-lookup"><span data-stu-id="e5261-109">ifTrue : 'T</span></span>

<span data-ttu-id="e5261-110">O valor a devolver quando `condition` `true` for.</span><span class="sxs-lookup"><span data-stu-id="e5261-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="e5261-111">ifFalse : 'T</span><span class="sxs-lookup"><span data-stu-id="e5261-111">ifFalse : 'T</span></span>

<span data-ttu-id="e5261-112">O valor a devolver quando `condition` `false` for.</span><span class="sxs-lookup"><span data-stu-id="e5261-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="e5261-113">Saída : 'T</span><span class="sxs-lookup"><span data-stu-id="e5261-113">Output : 'T</span></span>

<span data-ttu-id="e5261-114">`ifTrue` se `condition` `true` for, e `ifFalse` de outra forma.</span><span class="sxs-lookup"><span data-stu-id="e5261-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e5261-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e5261-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5261-116">'T</span><span class="sxs-lookup"><span data-stu-id="e5261-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e5261-117">Observações</span><span class="sxs-lookup"><span data-stu-id="e5261-117">Remarks</span></span>

<span data-ttu-id="e5261-118">Ao contrário do `?|` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.</span><span class="sxs-lookup"><span data-stu-id="e5261-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="e5261-119">Até um comportamento de curto-circuito, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="e5261-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```