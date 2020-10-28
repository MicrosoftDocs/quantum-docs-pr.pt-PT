---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: AplicarOperaçãoControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718354"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="98c75-102">AplicarOperaçãoControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="98c75-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="98c75-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="98c75-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="98c75-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98c75-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98c75-105">Aplica uma operação unitária no registo-alvo se o estado do registo de controlo corresponder a um número inteiro positivo especificado.</span><span class="sxs-lookup"><span data-stu-id="98c75-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="98c75-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="98c75-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="98c75-107">número Estado : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98c75-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98c75-108">Um inteiro não-alemão em que a operação `oracle` deve ser controlada.</span><span class="sxs-lookup"><span data-stu-id="98c75-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="98c75-109">oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="98c75-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="98c75-110">Uma operação unitária a ser controlada.</span><span class="sxs-lookup"><span data-stu-id="98c75-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="98c75-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="98c75-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="98c75-112">Um registo quântico que controla a aplicação de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="98c75-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="98c75-113">targetRegister : 'T</span><span class="sxs-lookup"><span data-stu-id="98c75-113">targetRegister : 'T</span></span>

<span data-ttu-id="98c75-114">Um registo sobre o qual se `oracle` candidatará.</span><span class="sxs-lookup"><span data-stu-id="98c75-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98c75-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98c75-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="98c75-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="98c75-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="98c75-117">'T</span><span class="sxs-lookup"><span data-stu-id="98c75-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="98c75-118">Observações</span><span class="sxs-lookup"><span data-stu-id="98c75-118">Remarks</span></span>

<span data-ttu-id="98c75-119">O valor `numberState` é interpretado usando uma codificação pouco endiana.</span><span class="sxs-lookup"><span data-stu-id="98c75-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="98c75-120">`numberState` deve ser no máximo $2^\texttt{Comprimento (controlRegister)} - 1$.</span><span class="sxs-lookup"><span data-stu-id="98c75-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="98c75-121">Por exemplo, `numberState = 537` significa que é aplicado se e `oracle` somente se estiver no estado `controlRegister` $\ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="98c75-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>