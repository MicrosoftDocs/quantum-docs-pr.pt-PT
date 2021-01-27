---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Aplicar operaçãoTorestA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841266"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="7d059-102">Aplicar operaçãoTorestA</span><span class="sxs-lookup"><span data-stu-id="7d059-102">ApplyToRestA operation</span></span>

<span data-ttu-id="7d059-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7d059-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7d059-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d059-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d059-105">Aplica uma operação a todos menos ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="7d059-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="7d059-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d059-106">Description</span></span>

<span data-ttu-id="7d059-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="7d059-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="7d059-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7d059-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="7d059-109">op : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="7d059-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7d059-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="7d059-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="7d059-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="7d059-111">targets : 'T[]</span></span>

<span data-ttu-id="7d059-112">Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="7d059-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d059-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d059-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7d059-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7d059-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d059-115">'T</span><span class="sxs-lookup"><span data-stu-id="7d059-115">'T</span></span>

<span data-ttu-id="7d059-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="7d059-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d059-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7d059-117">See Also</span></span>

- [<span data-ttu-id="7d059-118">Microsoft.Quantum.Canon.ApplyTorest</span><span class="sxs-lookup"><span data-stu-id="7d059-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="7d059-119">Microsoft.Quantum.Canon.ApplyTorestC</span><span class="sxs-lookup"><span data-stu-id="7d059-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="7d059-120">Microsoft.Quantum.Canon.applyTorestCA</span><span class="sxs-lookup"><span data-stu-id="7d059-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)