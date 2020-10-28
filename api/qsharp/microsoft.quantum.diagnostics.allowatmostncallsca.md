---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Permitir a operação DaMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713061"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="2f1db-102">Permitir a operação DaMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="2f1db-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="2f1db-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2f1db-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2f1db-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f1db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f1db-105">Entre uma chamada para esta operação e o seu adjacente, afirma que uma determinada operação é chamada no máximo um certo número de vezes.</span><span class="sxs-lookup"><span data-stu-id="2f1db-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2f1db-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2f1db-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="2f1db-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f1db-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f1db-108">O número máximo de vezes que `op` pode ser chamado.</span><span class="sxs-lookup"><span data-stu-id="2f1db-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="2f1db-109">op : 'TInput => 'TOutput Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="2f1db-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="2f1db-110">Uma operação cujas chamadas devem ser restringidas.</span><span class="sxs-lookup"><span data-stu-id="2f1db-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="2f1db-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2f1db-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2f1db-112">Uma mensagem a ser exibida após o fracasso.</span><span class="sxs-lookup"><span data-stu-id="2f1db-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f1db-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f1db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f1db-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2f1db-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="2f1db-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="2f1db-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="2f1db-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="2f1db-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="2f1db-117">Observações</span><span class="sxs-lookup"><span data-stu-id="2f1db-117">Remarks</span></span>

<span data-ttu-id="2f1db-118">Esta operação pode ser substituída por um não-operatório sobre alvos que não a suportem.</span><span class="sxs-lookup"><span data-stu-id="2f1db-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>