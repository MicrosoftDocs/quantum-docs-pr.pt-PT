---
uid: Microsoft.Quantum.Logical.Conditioned
title: Função condicionada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720790"
---
# <a name="conditioned-function"></a><span data-ttu-id="8a02a-102">Função condicionada</span><span class="sxs-lookup"><span data-stu-id="8a02a-102">Conditioned function</span></span>

<span data-ttu-id="8a02a-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8a02a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8a02a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a02a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a02a-105">Devolve um de dois valores, dependendo do valor de uma condição Booleana.</span><span class="sxs-lookup"><span data-stu-id="8a02a-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="8a02a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8a02a-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="8a02a-107">condição : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8a02a-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8a02a-108">Uma condição usada para controlar a entrada que é devolvida.</span><span class="sxs-lookup"><span data-stu-id="8a02a-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="8a02a-109">ifTrue : 'T</span><span class="sxs-lookup"><span data-stu-id="8a02a-109">ifTrue : 'T</span></span>

<span data-ttu-id="8a02a-110">O valor a devolver quando `condition` `true` for.</span><span class="sxs-lookup"><span data-stu-id="8a02a-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="8a02a-111">ifFalse : 'T</span><span class="sxs-lookup"><span data-stu-id="8a02a-111">ifFalse : 'T</span></span>

<span data-ttu-id="8a02a-112">O valor a devolver quando `condition` `false` for.</span><span class="sxs-lookup"><span data-stu-id="8a02a-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="8a02a-113">Saída : 'T</span><span class="sxs-lookup"><span data-stu-id="8a02a-113">Output : 'T</span></span>

<span data-ttu-id="8a02a-114">`ifTrue` se `condition` `true` for, e `ifFalse` de outra forma.</span><span class="sxs-lookup"><span data-stu-id="8a02a-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8a02a-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8a02a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a02a-116">'T</span><span class="sxs-lookup"><span data-stu-id="8a02a-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="8a02a-117">Observações</span><span class="sxs-lookup"><span data-stu-id="8a02a-117">Remarks</span></span>

<span data-ttu-id="8a02a-118">Ao contrário do `?|` operador, esta função não faz um curto-circuito, de modo a que ambas as entradas sejam totalmente avaliadas.</span><span class="sxs-lookup"><span data-stu-id="8a02a-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="8a02a-119">Até um comportamento de curto-circuito, os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="8a02a-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```