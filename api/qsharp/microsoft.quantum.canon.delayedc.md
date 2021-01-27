---
uid: Microsoft.Quantum.Canon.DelayedC
title: Função Dedesemtração
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840566"
---
# <a name="delayedc-function"></a><span data-ttu-id="37027-102">Função Dedesemtração</span><span class="sxs-lookup"><span data-stu-id="37027-102">DelayedC function</span></span>

<span data-ttu-id="37027-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="37027-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="37027-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37027-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37027-105">Devolve uma operação que se aplica a uma determinada operação com um argumento dado.</span><span class="sxs-lookup"><span data-stu-id="37027-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="37027-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="37027-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="37027-107">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="37027-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="37027-108">Uma operação a aplicar como resultado da aplicação do valor de retorno</span><span class="sxs-lookup"><span data-stu-id="37027-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="37027-109">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="37027-109">arg : 'T</span></span>

<span data-ttu-id="37027-110">A entrada à qual a operação `op` é aplicada.</span><span class="sxs-lookup"><span data-stu-id="37027-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="37027-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit) => [unitária](xref:microsoft.quantum.lang-ref.unit)  é CTL</span><span class="sxs-lookup"><span data-stu-id="37027-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="37027-112">Uma nova operação que se aplica `op` com a entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="37027-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="37027-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="37027-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37027-114">'T</span><span class="sxs-lookup"><span data-stu-id="37027-114">'T</span></span>

<span data-ttu-id="37027-115">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="37027-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="37027-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="37027-116">See Also</span></span>

- [<span data-ttu-id="37027-117">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="37027-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="37027-118">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="37027-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)