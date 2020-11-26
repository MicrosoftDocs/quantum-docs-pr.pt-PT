---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Aplicar operação ControlledOnBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219078"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="fa6d8-102">Aplicar operação ControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="fa6d8-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="fa6d8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fa6d8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fa6d8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa6d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa6d8-105">Aplica uma operação unitária no registo-alvo, controlada num estado especificado por uma determinada máscara de bit.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fa6d8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fa6d8-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="fa6d8-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="fa6d8-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="fa6d8-108">O fio da broca para controlar a operação unitária dada.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="fa6d8-109">oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="fa6d8-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fa6d8-110">A operação unitária a aplicar no registo-alvo.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="fa6d8-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fa6d8-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fa6d8-112">Um registo quântico que controla a aplicação de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="fa6d8-113">targetRegister : 'T</span><span class="sxs-lookup"><span data-stu-id="fa6d8-113">targetRegister : 'T</span></span>

<span data-ttu-id="fa6d8-114">O registo-alvo a ser passado `oracle` como entrada.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa6d8-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa6d8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fa6d8-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="fa6d8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa6d8-117">'T</span><span class="sxs-lookup"><span data-stu-id="fa6d8-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="fa6d8-118">Observações</span><span class="sxs-lookup"><span data-stu-id="fa6d8-118">Remarks</span></span>

<span data-ttu-id="fa6d8-119">O padrão dado pode `bits` ser mais curto do `controlRegister` que, caso em que os qubits de controlo adicionais são ignorados (isto é, nem controlados em $\ket {0} $ nem $\ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="fa6d8-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="fa6d8-120">Se `bits` for mais longo do que , um erro é `controlRegister` levantado.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="fa6d8-121">Por exemplo, `bits = [0,1,0,0,1]` significa que é aplicado se e `oracle` somente se estiver no estado `controlRegister` {0} $\ket {1} \ket {0} \ket {0} \ket \ket {1} \ket \ket $.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>