---
uid: Microsoft.Quantum.Canon.DelayedCA
title: Função DeDCA atrasada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: c44e3448c471f2a20f995d4546ee54f3affb726e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840557"
---
# <a name="delayedca-function"></a><span data-ttu-id="b9dd2-102">Função DeDCA atrasada</span><span class="sxs-lookup"><span data-stu-id="b9dd2-102">DelayedCA function</span></span>

<span data-ttu-id="b9dd2-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b9dd2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b9dd2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9dd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9dd2-105">Devolve uma operação que se aplica a uma determinada operação com um argumento dado.</span><span class="sxs-lookup"><span data-stu-id="b9dd2-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="b9dd2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b9dd2-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="b9dd2-107">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="b9dd2-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b9dd2-108">Uma operação a aplicar como resultado da aplicação do valor de retorno</span><span class="sxs-lookup"><span data-stu-id="b9dd2-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="b9dd2-109">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="b9dd2-109">arg : 'T</span></span>

<span data-ttu-id="b9dd2-110">A entrada à qual a operação `op` é aplicada.</span><span class="sxs-lookup"><span data-stu-id="b9dd2-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="b9dd2-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit) => [unitária](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="b9dd2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b9dd2-112">Uma nova operação que se aplica `op` com a entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="b9dd2-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b9dd2-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b9dd2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b9dd2-114">'T</span><span class="sxs-lookup"><span data-stu-id="b9dd2-114">'T</span></span>

<span data-ttu-id="b9dd2-115">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="b9dd2-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9dd2-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b9dd2-116">See Also</span></span>

- [<span data-ttu-id="b9dd2-117">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="b9dd2-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="b9dd2-118">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="b9dd2-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)