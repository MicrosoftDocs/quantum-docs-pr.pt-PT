---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: AplicarOperaçãoToTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850445"
---
# <a name="applytotail-operation"></a><span data-ttu-id="0f0e5-102">AplicarOperaçãoToTail</span><span class="sxs-lookup"><span data-stu-id="0f0e5-102">ApplyToTail operation</span></span>

<span data-ttu-id="0f0e5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f0e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f0e5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f0e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f0e5-105">Aplica uma operação ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="0f0e5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0f0e5-106">Description</span></span>

<span data-ttu-id="0f0e5-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="0f0e5-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="0f0e5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="0f0e5-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="0f0e5-109">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0f0e5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0f0e5-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0f0e5-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="0f0e5-111">targets : 'T[]</span></span>

<span data-ttu-id="0f0e5-112">Uma série de alvos, dos quais o último será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="0f0e5-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f0e5-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f0e5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0f0e5-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0f0e5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f0e5-115">'T</span><span class="sxs-lookup"><span data-stu-id="0f0e5-115">'T</span></span>

<span data-ttu-id="0f0e5-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="0f0e5-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0f0e5-117">Example</span></span>

<span data-ttu-id="0f0e5-118">Os seguintes cortes Q# são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="0f0e5-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="0f0e5-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0f0e5-119">See Also</span></span>

- [<span data-ttu-id="0f0e5-120">Microsoft.Quantum.Canon.ApplyToTaila</span><span class="sxs-lookup"><span data-stu-id="0f0e5-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="0f0e5-121">Microsoft.Quantum.Canon.ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="0f0e5-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="0f0e5-122">Microsoft.Quantum.Canon.ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="0f0e5-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)