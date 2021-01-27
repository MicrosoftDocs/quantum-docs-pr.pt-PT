---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Permitir a operação DaMostNCallsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853527"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="421ef-102">Permitir a operação DaMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="421ef-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="421ef-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="421ef-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="421ef-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="421ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="421ef-105">Entre uma chamada para esta operação e o seu adjacente, afirma que uma determinada operação é chamada no máximo um certo número de vezes.</span><span class="sxs-lookup"><span data-stu-id="421ef-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="421ef-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="421ef-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="421ef-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="421ef-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="421ef-108">O número máximo de vezes que `op` pode ser chamado.</span><span class="sxs-lookup"><span data-stu-id="421ef-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="421ef-109">op : 'TInput => 'TOutput é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="421ef-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="421ef-110">Uma operação cujas chamadas devem ser restringidas.</span><span class="sxs-lookup"><span data-stu-id="421ef-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="421ef-111">mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="421ef-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="421ef-112">Uma mensagem a ser exibida após o fracasso.</span><span class="sxs-lookup"><span data-stu-id="421ef-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="421ef-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="421ef-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="421ef-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="421ef-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="421ef-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="421ef-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="421ef-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="421ef-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="421ef-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="421ef-117">Example</span></span>

<span data-ttu-id="421ef-118">O seguinte corte falhará quando executado em máquinas que suportam este diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="421ef-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="421ef-119">Observações</span><span class="sxs-lookup"><span data-stu-id="421ef-119">Remarks</span></span>

<span data-ttu-id="421ef-120">Esta operação pode ser substituída por um não-operatório sobre alvos que não a suportem.</span><span class="sxs-lookup"><span data-stu-id="421ef-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>