---
uid: Microsoft.Quantum.Canon.DelayedC
title: Função Dedesemtração
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207021"
---
# <a name="delayedc-function"></a><span data-ttu-id="e450a-102">Função Dedesemtração</span><span class="sxs-lookup"><span data-stu-id="e450a-102">DelayedC function</span></span>

<span data-ttu-id="e450a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e450a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e450a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e450a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e450a-105">Devolve uma operação que se aplica a uma determinada operação com um argumento dado.</span><span class="sxs-lookup"><span data-stu-id="e450a-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="e450a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e450a-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="e450a-107">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="e450a-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e450a-108">Uma operação a aplicar como resultado da aplicação do valor de retorno</span><span class="sxs-lookup"><span data-stu-id="e450a-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="e450a-109">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="e450a-109">arg : 'T</span></span>

<span data-ttu-id="e450a-110">A entrada à qual a operação `op` é aplicada.</span><span class="sxs-lookup"><span data-stu-id="e450a-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="e450a-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit) => [unitária](xref:microsoft.quantum.lang-ref.unit)  é CTL</span><span class="sxs-lookup"><span data-stu-id="e450a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e450a-112">Uma nova operação que se aplica `op` com a entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="e450a-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e450a-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e450a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e450a-114">'T</span><span class="sxs-lookup"><span data-stu-id="e450a-114">'T</span></span>

<span data-ttu-id="e450a-115">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="e450a-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="e450a-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e450a-116">See Also</span></span>

- [<span data-ttu-id="e450a-117">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="e450a-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="e450a-118">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="e450a-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)