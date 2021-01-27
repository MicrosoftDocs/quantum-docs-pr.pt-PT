---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: AplicaxControlledOnTruthTable
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 6e956038f7cd15db7348ff830da8bc9eae53aa61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855552"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="0083d-102">AplicaxControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="0083d-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="0083d-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0083d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0083d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0083d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0083d-105">Aplica a @"microsoft.quantum.intrinsic.x" operação em `target` , se a função Boolean `func` avaliar a verdade para a atribuição clássica em `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="0083d-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0083d-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0083d-106">Description</span></span>

<span data-ttu-id="0083d-107">A operação implementa a operação unitária \start{align} U\ket{x}ket{y} = \ket{x}ket{y \oplus f(x)} \end{align} onde $x$ e $y$ representam `controlRegister` `target` e, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0083d-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="0083d-108">A função Booleana $f$ é representada como uma mesa de verdade em termos de um grande número inteiro.</span><span class="sxs-lookup"><span data-stu-id="0083d-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="0083d-109">Por exemplo, a função maioritária em três entradas é representada pelo bitstring `11101000` , onde a parte mais significativa corresponde à atribuição de entrada , e a parte menos significativa `1` corresponde à atribuição de entrada `(1, 1, 1)` `0` `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="0083d-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="0083d-110">Pode ser representado pelo grande número inteiro `0xE8L` na notação hexadecimal ou como `232L` na notação decimal.</span><span class="sxs-lookup"><span data-stu-id="0083d-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="0083d-111">O `L` sufixo indica que a constante é do tipo `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="0083d-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="0083d-112">Mais detalhes sobre esta representação também podem ser encontrados nas tabelas da [verdade kata.](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)</span><span class="sxs-lookup"><span data-stu-id="0083d-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="0083d-113">A implementação faz uso e @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" portões.</span><span class="sxs-lookup"><span data-stu-id="0083d-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="0083d-114">Entrada</span><span class="sxs-lookup"><span data-stu-id="0083d-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="0083d-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0083d-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0083d-116">Mesa da verdade booleana representada como grande inteiro</span><span class="sxs-lookup"><span data-stu-id="0083d-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="0083d-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0083d-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0083d-118">Registo de qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="0083d-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0083d-119">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0083d-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0083d-120">Qubit alvo</span><span class="sxs-lookup"><span data-stu-id="0083d-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="0083d-121">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0083d-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="0083d-122">Referências</span><span class="sxs-lookup"><span data-stu-id="0083d-122">References</span></span>

- [<span data-ttu-id="0083d-123">*N. Schuch*, *J. Siewert*, PRL 91, nº 027902, 2003, arXiv:quant-ph/0303063</span><span class="sxs-lookup"><span data-stu-id="0083d-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="0083d-124">*Mathias Soeken*, *Martin Roetteler,* arXiv:2005.12310</span><span class="sxs-lookup"><span data-stu-id="0083d-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="0083d-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0083d-125">See Also</span></span>

- [<span data-ttu-id="0083d-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="0083d-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)