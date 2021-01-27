---
uid: Microsoft.Quantum.Canon.CControlledA
title: Função CControlledA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 823d80182621691f4fa6f42246b3d671f3adfc3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840999"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="44a85-102">Função CControlledA</span><span class="sxs-lookup"><span data-stu-id="44a85-102">CControlledA function</span></span>

<span data-ttu-id="44a85-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="44a85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="44a85-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44a85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44a85-105">Dada uma operação, devolve uma nova operação que aplica a operação se uma parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="44a85-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="44a85-106">Se `false` nada acontecer.</span><span class="sxs-lookup"><span data-stu-id="44a85-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="44a85-107">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="44a85-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="44a85-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="44a85-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="44a85-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="44a85-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="44a85-110">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="44a85-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj"></a><span data-ttu-id="44a85-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T) = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="44a85-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="44a85-112">Uma nova operação que é operação se a parte de controlo clássico for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="44a85-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="44a85-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="44a85-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="44a85-114">'T</span><span class="sxs-lookup"><span data-stu-id="44a85-114">'T</span></span>

<span data-ttu-id="44a85-115">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="44a85-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="44a85-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="44a85-116">See Also</span></span>

- [<span data-ttu-id="44a85-117">Microsoft.Quantum.Canon.CControlled</span><span class="sxs-lookup"><span data-stu-id="44a85-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)