---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Função ControlledOnInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207263"
---
# <a name="controlledonint-function"></a><span data-ttu-id="47a40-102">Função ControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="47a40-102">ControlledOnInt function</span></span>

<span data-ttu-id="47a40-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47a40-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47a40-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47a40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47a40-105">Devolve um operador unitário que aplica um oráculo no registo-alvo se o estado do registo de controlo corresponder a um número inteiro positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="47a40-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="47a40-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="47a40-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="47a40-107">número Estado : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="47a40-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="47a40-108">Inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="47a40-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="47a40-109">oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="47a40-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="47a40-110">Operador unitário.</span><span class="sxs-lookup"><span data-stu-id="47a40-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="47a40-111">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="47a40-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="47a40-112">Um operador unitário que se aplique `oracle` no registo-alvo se o estado do registo de controlo corresponder ao estado do número `numberState` .</span><span class="sxs-lookup"><span data-stu-id="47a40-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="47a40-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="47a40-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47a40-114">'T</span><span class="sxs-lookup"><span data-stu-id="47a40-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="47a40-115">Observações</span><span class="sxs-lookup"><span data-stu-id="47a40-115">Remarks</span></span>

<span data-ttu-id="47a40-116">O valor `numberState` é interpretado usando uma codificação pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="47a40-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>