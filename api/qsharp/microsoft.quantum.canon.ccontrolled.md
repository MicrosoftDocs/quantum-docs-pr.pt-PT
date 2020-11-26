---
uid: Microsoft.Quantum.Canon.CControlled
title: Função CControled
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: 76e663e9a4b53c7ed74a1b70da516fb07958923b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216901"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="f79d6-102">Função CControled</span><span class="sxs-lookup"><span data-stu-id="f79d6-102">CControlled function</span></span>

<span data-ttu-id="f79d6-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f79d6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f79d6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f79d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f79d6-105">Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="f79d6-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="f79d6-106">Se `false` nada acontecer.</span><span class="sxs-lookup"><span data-stu-id="f79d6-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="f79d6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f79d6-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="f79d6-108">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f79d6-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f79d6-109">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f79d6-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="f79d6-110">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f79d6-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f79d6-111">Uma nova operação que é operação se a parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="f79d6-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f79d6-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f79d6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f79d6-113">'T</span><span class="sxs-lookup"><span data-stu-id="f79d6-113">'T</span></span>

<span data-ttu-id="f79d6-114">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f79d6-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f79d6-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f79d6-115">See Also</span></span>

- [<span data-ttu-id="f79d6-116">Microsoft.Quantum.Canon.CControlledC</span><span class="sxs-lookup"><span data-stu-id="f79d6-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="f79d6-117">Microsoft.Quantum.Canon.CControlleda</span><span class="sxs-lookup"><span data-stu-id="f79d6-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="f79d6-118">Microsoft.Quantum.Canon.CControlledCA</span><span class="sxs-lookup"><span data-stu-id="f79d6-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)