---
uid: Microsoft.Quantum.Canon.DelayedA
title: Função DelayA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716250"
---
# <a name="delayeda-function"></a><span data-ttu-id="71655-102">Função DelayA</span><span class="sxs-lookup"><span data-stu-id="71655-102">DelayedA function</span></span>

<span data-ttu-id="71655-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71655-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71655-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71655-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71655-105">Devolve uma operação que se aplica a uma determinada operação com um argumento dado.</span><span class="sxs-lookup"><span data-stu-id="71655-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="71655-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="71655-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="71655-107">op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj</span><span class="sxs-lookup"><span data-stu-id="71655-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="71655-108">Uma operação a aplicar como resultado da aplicação do valor de retorno</span><span class="sxs-lookup"><span data-stu-id="71655-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="71655-109">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="71655-109">arg : 'T</span></span>

<span data-ttu-id="71655-110">A entrada à qual a operação `op` é aplicada.</span><span class="sxs-lookup"><span data-stu-id="71655-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="71655-111">Saída [Unit](xref:microsoft.quantum.lang-ref.unit) : => [Unidade Unidade](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="71655-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="71655-112">Uma nova operação que se aplica `op` com a entrada `arg`</span><span class="sxs-lookup"><span data-stu-id="71655-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="71655-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="71655-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71655-114">'T</span><span class="sxs-lookup"><span data-stu-id="71655-114">'T</span></span>

<span data-ttu-id="71655-115">O tipo de entrada da operação a ser adiado.</span><span class="sxs-lookup"><span data-stu-id="71655-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="71655-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="71655-116">See Also</span></span>

- [<span data-ttu-id="71655-117">Microsoft.Quantum.Canon.Adiado</span><span class="sxs-lookup"><span data-stu-id="71655-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="71655-118">Microsoft.Quantum.Canon.Delay</span><span class="sxs-lookup"><span data-stu-id="71655-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)