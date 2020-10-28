---
uid: Microsoft.Quantum.Canon.CControlledC
title: Função CControlledC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716575"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="fc880-102">Função CControlledC</span><span class="sxs-lookup"><span data-stu-id="fc880-102">CControlledC function</span></span>

<span data-ttu-id="fc880-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fc880-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fc880-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc880-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc880-105">Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="fc880-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="fc880-106">Se `false` nada acontecer.</span><span class="sxs-lookup"><span data-stu-id="fc880-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="fc880-107">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="fc880-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="fc880-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fc880-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="fc880-109">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="fc880-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="fc880-110">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fc880-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="fc880-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="fc880-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="fc880-112">Uma nova operação que é operação se a parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="fc880-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fc880-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="fc880-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc880-114">'T</span><span class="sxs-lookup"><span data-stu-id="fc880-114">'T</span></span>

<span data-ttu-id="fc880-115">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fc880-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc880-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fc880-116">See Also</span></span>

- [<span data-ttu-id="fc880-117">Microsoft.Quantum.Canon.CControlled</span><span class="sxs-lookup"><span data-stu-id="fc880-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)