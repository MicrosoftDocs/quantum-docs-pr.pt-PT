---
uid: Microsoft.Quantum.Canon.CurriedOp
title: Função CurriedOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840774"
---
# <a name="curriedop-function"></a><span data-ttu-id="8c5db-102">Função CurriedOp</span><span class="sxs-lookup"><span data-stu-id="8c5db-102">CurriedOp function</span></span>

<span data-ttu-id="8c5db-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c5db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c5db-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c5db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c5db-105">Devolve uma versão cosidada de uma operação em duas entradas.</span><span class="sxs-lookup"><span data-stu-id="8c5db-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="8c5db-106">Ou seja, dada uma operação com duas entradas, esta função aplica o isomorfismo de Curry $f(x, y) \equiv f(x)(y)$ para devolver uma operação de uma entrada que devolve uma operação de uma entrada.</span><span class="sxs-lookup"><span data-stu-id="8c5db-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="8c5db-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8c5db-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="8c5db-108">op : ('T,'U) = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8c5db-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8c5db-109">Uma operação cuja entrada é um par.</span><span class="sxs-lookup"><span data-stu-id="8c5db-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="8c5db-110">Saída : 'T-> 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8c5db-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8c5db-111">Uma operação que aceite o primeiro elemento de um par e devolva uma operação que aceite como entrada o segundo elemento da entrada da operação original.</span><span class="sxs-lookup"><span data-stu-id="8c5db-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8c5db-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8c5db-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8c5db-113">'T</span><span class="sxs-lookup"><span data-stu-id="8c5db-113">'T</span></span>

<span data-ttu-id="8c5db-114">O tipo de primeiro componente de uma função definida em pares.</span><span class="sxs-lookup"><span data-stu-id="8c5db-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="8c5db-115">'U</span><span class="sxs-lookup"><span data-stu-id="8c5db-115">'U</span></span>

<span data-ttu-id="8c5db-116">O tipo do segundo componente de uma função definida em pares.</span><span class="sxs-lookup"><span data-stu-id="8c5db-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c5db-117">Observações</span><span class="sxs-lookup"><span data-stu-id="8c5db-117">Remarks</span></span>

<span data-ttu-id="8c5db-118">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="8c5db-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```