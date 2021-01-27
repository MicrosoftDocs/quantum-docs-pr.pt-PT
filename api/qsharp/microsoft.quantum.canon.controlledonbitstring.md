---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Função ControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840809"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="eeb69-102">Função ControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="eeb69-102">ControlledOnBitString function</span></span>

<span data-ttu-id="eeb69-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eeb69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eeb69-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eeb69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eeb69-105">Devolve uma operação unitária que aplica um oráculo no registo-alvo se o estado do registo de controlo corresponder a uma máscara de bits especificada.</span><span class="sxs-lookup"><span data-stu-id="eeb69-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="eeb69-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="eeb69-106">Description</span></span>

<span data-ttu-id="eeb69-107">A saída desta função é uma operação que pode ser representada por uma transformação unitária $U$ de tal forma que \start{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{{b_0 b_1 \cdots b_{n-1}} \otimes \start{} ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{de outra forma} \end{cases}, \end{align} onde $V$ é uma transformação unitária que representa a ação da `oracle` operação.</span><span class="sxs-lookup"><span data-stu-id="eeb69-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="eeb69-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="eeb69-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="eeb69-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="eeb69-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="eeb69-110">O fio da broca para controlar a operação unitária dada.</span><span class="sxs-lookup"><span data-stu-id="eeb69-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="eeb69-111">oráculo : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="eeb69-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="eeb69-112">A operação unitária a aplicar no registo-alvo.</span><span class="sxs-lookup"><span data-stu-id="eeb69-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="eeb69-113">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="eeb69-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="eeb69-114">Uma operação unitária que se aplica `oracle` no registo-alvo se o estado do registo de controlo corresponder à máscara de `bits` bits .</span><span class="sxs-lookup"><span data-stu-id="eeb69-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="eeb69-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="eeb69-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eeb69-116">'T</span><span class="sxs-lookup"><span data-stu-id="eeb69-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="eeb69-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eeb69-117">Example</span></span>

<span data-ttu-id="eeb69-118">Os seguintes fragmentos de código são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="eeb69-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="eeb69-119">e</span><span class="sxs-lookup"><span data-stu-id="eeb69-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="eeb69-120">O seguinte código prepara um estado $\frac {1} {2} (\ket {00} - \ket {01} + \ket {10} + \ket + \ket {11} )$:</span><span class="sxs-lookup"><span data-stu-id="eeb69-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="eeb69-121">Observações</span><span class="sxs-lookup"><span data-stu-id="eeb69-121">Remarks</span></span>

<span data-ttu-id="eeb69-122">O padrão dado pode `bits` ser mais curto do `controlRegister` que, caso em que os qubits de controlo adicionais são ignorados (isto é, nem controlados em $\ket {0} $ nem $\ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="eeb69-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="eeb69-123">Se `bits` for mais longo do que , um erro é `controlRegister` levantado.</span><span class="sxs-lookup"><span data-stu-id="eeb69-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="eeb69-124">Dada uma matriz `bits` Booleana e uma operação unitária, a saída desta `oracle` função é uma operação que executa os seguintes passos:</span><span class="sxs-lookup"><span data-stu-id="eeb69-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="eeb69-125">Aplicar uma `X` operação a cada qubit do registo de controlo que corresponda ao `false` elemento `bits` do;</span><span class="sxs-lookup"><span data-stu-id="eeb69-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="eeb69-126">aplicar-se `Controlled oracle` aos registos de controlo e de destino;</span><span class="sxs-lookup"><span data-stu-id="eeb69-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="eeb69-127">aplicar uma `X` operação a cada qubit do registo de controlo que corresponda ao `false` elemento da nova volta para devolver o registo de controlo ao estado `bits` original.</span><span class="sxs-lookup"><span data-stu-id="eeb69-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="eeb69-128">A saída do `Controlled` functor é um caso especial de `ControlledOnBitString` onde é igual a `bits` `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="eeb69-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>