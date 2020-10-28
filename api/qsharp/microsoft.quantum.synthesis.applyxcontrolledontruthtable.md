---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: AplicaxControlledOnTruthTable
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725245"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="9d060-102">AplicaxControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="9d060-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="9d060-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9d060-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9d060-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d060-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d060-105">Aplica a @"microsoft.quantum.intrinsic.x" operação em `target` , se a função Boolean `func` avaliar a verdade para a atribuição clássica em `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="9d060-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="9d060-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d060-106">Description</span></span>

<span data-ttu-id="9d060-107">A operação implementa a operação unitária \start{align} U\ket{x}ket{y} = \ket{x}ket{y \oplus f(x)} \end{align} onde $x$ e $y$ representam `controlRegister` `target` e, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9d060-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="9d060-108">A função Booleana $f$ é representada como uma mesa de verdade em termos de um grande número inteiro.</span><span class="sxs-lookup"><span data-stu-id="9d060-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="9d060-109">Por exemplo, a função maioritária em três entradas é representada pelo bitstring `11101000` , onde a parte mais significativa corresponde à atribuição de entrada , e a parte menos significativa `1` corresponde à atribuição de entrada `(1, 1, 1)` `0` `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="9d060-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="9d060-110">Pode ser representado pelo grande número inteiro `0xE8L` na notação hexadecimal ou como `232L` na notação decimal.</span><span class="sxs-lookup"><span data-stu-id="9d060-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="9d060-111">O `L` sufixo indica que a constante é do tipo `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="9d060-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="9d060-112">Mais detalhes sobre esta representação também podem ser encontrados nas tabelas da [verdade kata.](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)</span><span class="sxs-lookup"><span data-stu-id="9d060-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="9d060-113">A implementação faz uso e @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" portões.</span><span class="sxs-lookup"><span data-stu-id="9d060-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="9d060-114">Entrada</span><span class="sxs-lookup"><span data-stu-id="9d060-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="9d060-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9d060-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9d060-116">Mesa da verdade booleana representada como grande inteiro</span><span class="sxs-lookup"><span data-stu-id="9d060-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="9d060-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9d060-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9d060-118">Registo de qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="9d060-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9d060-119">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9d060-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9d060-120">Qubit alvo</span><span class="sxs-lookup"><span data-stu-id="9d060-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d060-121">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d060-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9d060-122">Referências</span><span class="sxs-lookup"><span data-stu-id="9d060-122">References</span></span>

- [<span data-ttu-id="9d060-123">*N. Schuch* , *J. Siewert* , PRL 91, nº 027902, 2003, arXiv:quant-ph/0303063</span><span class="sxs-lookup"><span data-stu-id="9d060-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="9d060-124">*Mathias Soeken* , *Martin Roetteler,* arXiv:2005.12310</span><span class="sxs-lookup"><span data-stu-id="9d060-124">*Mathias Soeken* , *Martin Roetteler* , arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="9d060-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9d060-125">See Also</span></span>

- [<span data-ttu-id="9d060-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="9d060-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)