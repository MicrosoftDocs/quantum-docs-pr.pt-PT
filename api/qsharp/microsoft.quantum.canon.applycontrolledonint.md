---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: AplicarOperaçãoControlledOnInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3dd17e6bc913e84941a6b81f134e60536a4c4122
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219010"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="6623a-102">AplicarOperaçãoControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="6623a-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="6623a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6623a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6623a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6623a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6623a-105">Aplica uma operação unitária no registo-alvo se o estado do registo de controlo corresponder a um número inteiro positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="6623a-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6623a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6623a-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="6623a-107">número Estado : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6623a-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6623a-108">Um inteiro não-alemão em que a operação `oracle` deve ser controlada.</span><span class="sxs-lookup"><span data-stu-id="6623a-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="6623a-109">oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="6623a-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6623a-110">Uma operação unitária a ser controlada.</span><span class="sxs-lookup"><span data-stu-id="6623a-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="6623a-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6623a-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6623a-112">Um registo quântico que controla a aplicação de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="6623a-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="6623a-113">targetRegister : 'T</span><span class="sxs-lookup"><span data-stu-id="6623a-113">targetRegister : 'T</span></span>

<span data-ttu-id="6623a-114">Um registo sobre o qual se `oracle` candidatará.</span><span class="sxs-lookup"><span data-stu-id="6623a-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6623a-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6623a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6623a-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="6623a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6623a-117">'T</span><span class="sxs-lookup"><span data-stu-id="6623a-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6623a-118">Observações</span><span class="sxs-lookup"><span data-stu-id="6623a-118">Remarks</span></span>

<span data-ttu-id="6623a-119">O valor `numberState` é interpretado usando uma codificação pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="6623a-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="6623a-120">`numberState` deve ser no máximo $2^\texttt{Comprimento (controlRegister)} - 1$.</span><span class="sxs-lookup"><span data-stu-id="6623a-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="6623a-121">Por exemplo, `numberState = 537` significa que é aplicado se e `oracle` somente se estiver no estado `controlRegister` $\ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="6623a-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>