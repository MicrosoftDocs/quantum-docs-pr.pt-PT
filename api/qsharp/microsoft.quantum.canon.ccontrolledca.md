---
uid: Microsoft.Quantum.Canon.CControlledCA
title: Função CControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716572"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="727ea-102">Função CControlledCA</span><span class="sxs-lookup"><span data-stu-id="727ea-102">CControlledCA function</span></span>

<span data-ttu-id="727ea-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="727ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="727ea-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="727ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="727ea-105">Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="727ea-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="727ea-106">Se `false` nada acontecer.</span><span class="sxs-lookup"><span data-stu-id="727ea-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="727ea-107">O modificador `CA` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="727ea-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="727ea-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="727ea-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="727ea-109">op : 'T = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit) + Adj</span><span class="sxs-lookup"><span data-stu-id="727ea-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="727ea-110">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="727ea-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="727ea-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span><span class="sxs-lookup"><span data-stu-id="727ea-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="727ea-112">Uma nova operação que é operação se a parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="727ea-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="727ea-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="727ea-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="727ea-114">'T</span><span class="sxs-lookup"><span data-stu-id="727ea-114">'T</span></span>

<span data-ttu-id="727ea-115">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="727ea-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="727ea-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="727ea-116">See Also</span></span>

- [<span data-ttu-id="727ea-117">Microsoft.Quantum.Canon.CControlled</span><span class="sxs-lookup"><span data-stu-id="727ea-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)