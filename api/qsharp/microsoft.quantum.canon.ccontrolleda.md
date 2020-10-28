---
uid: Microsoft.Quantum.Canon.CControlledA
title: Função CControlledA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716586"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="f4cc8-102">Função CControlledA</span><span class="sxs-lookup"><span data-stu-id="f4cc8-102">CControlledA function</span></span>

<span data-ttu-id="f4cc8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4cc8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4cc8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4cc8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4cc8-105">Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="f4cc8-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="f4cc8-106">Se `false` nada acontecer.</span><span class="sxs-lookup"><span data-stu-id="f4cc8-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="f4cc8-107">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="f4cc8-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="f4cc8-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f4cc8-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="f4cc8-109">op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj</span><span class="sxs-lookup"><span data-stu-id="f4cc8-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f4cc8-110">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f4cc8-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="f4cc8-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="f4cc8-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f4cc8-112">Uma nova operação que é operação se a parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="f4cc8-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f4cc8-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f4cc8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4cc8-114">'T</span><span class="sxs-lookup"><span data-stu-id="f4cc8-114">'T</span></span>

<span data-ttu-id="f4cc8-115">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f4cc8-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4cc8-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f4cc8-116">See Also</span></span>

- [<span data-ttu-id="f4cc8-117">Microsoft.Quantum.Canon.CControlled</span><span class="sxs-lookup"><span data-stu-id="f4cc8-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)