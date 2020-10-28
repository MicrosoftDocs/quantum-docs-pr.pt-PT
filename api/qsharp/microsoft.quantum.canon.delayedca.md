---
uid: Microsoft.Quantum.Canon.DelayedCA
title: Função DeDCA atrasada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716222"
---
# <a name="delayedca-function"></a><span data-ttu-id="d93d5-102">Função DeDCA atrasada</span><span class="sxs-lookup"><span data-stu-id="d93d5-102">DelayedCA function</span></span>

<span data-ttu-id="d93d5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d93d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d93d5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d93d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d93d5-105">Devolve uma operação que se aplica a uma determinada operação com um argumento dado.</span><span class="sxs-lookup"><span data-stu-id="d93d5-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="d93d5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d93d5-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="d93d5-107">op : 'T = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit) + Adj</span><span class="sxs-lookup"><span data-stu-id="d93d5-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d93d5-108">Uma operação a aplicar como resultado da aplicação do valor de retorno</span><span class="sxs-lookup"><span data-stu-id="d93d5-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="d93d5-109">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="d93d5-109">arg : 'T</span></span>

<span data-ttu-id="d93d5-110">A entrada à qual a operação `op` é aplicada.</span><span class="sxs-lookup"><span data-stu-id="d93d5-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="d93d5-111">Saída [Unit](xref:microsoft.quantum.lang-ref.unit) : => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span><span class="sxs-lookup"><span data-stu-id="d93d5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d93d5-112">Uma nova operação que se aplica `op` com a entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="d93d5-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d93d5-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d93d5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d93d5-114">'T</span><span class="sxs-lookup"><span data-stu-id="d93d5-114">'T</span></span>

<span data-ttu-id="d93d5-115">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="d93d5-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d93d5-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d93d5-116">See Also</span></span>

- [<span data-ttu-id="d93d5-117">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="d93d5-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="d93d5-118">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="d93d5-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)