---
uid: Microsoft.Quantum.Canon.CControlledCA
title: Função CControlledCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: cc1a783dfbf97afae50f4b42e66cba2b2a2ec833
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207433"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="8599b-102">Função CControlledCA</span><span class="sxs-lookup"><span data-stu-id="8599b-102">CControlledCA function</span></span>

<span data-ttu-id="8599b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8599b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8599b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8599b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8599b-105">Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="8599b-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="8599b-106">Se `false` nada acontecer.</span><span class="sxs-lookup"><span data-stu-id="8599b-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="8599b-107">O modificador `CA` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="8599b-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="8599b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="8599b-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="8599b-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8599b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8599b-110">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="8599b-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="8599b-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8599b-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8599b-112">Uma nova operação que é operação se a parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="8599b-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8599b-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8599b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8599b-114">'T</span><span class="sxs-lookup"><span data-stu-id="8599b-114">'T</span></span>

<span data-ttu-id="8599b-115">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="8599b-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8599b-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8599b-116">See Also</span></span>

- [<span data-ttu-id="8599b-117">Microsoft.Quantum.Canon.CControlled</span><span class="sxs-lookup"><span data-stu-id="8599b-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)