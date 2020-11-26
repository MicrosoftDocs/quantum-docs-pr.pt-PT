---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: AplicaXControlledOnTruthTableWithCleanTarget
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203268"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="cd119-102">AplicaXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="cd119-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="cd119-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="cd119-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="cd119-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd119-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd119-105">Aplica a @"microsoft.quantum.intrinsic.x" operação em `target` , se a função Boolean `func` avaliar a verdade para a atribuição clássica em `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="cd119-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="cd119-106">Description</span><span class="sxs-lookup"><span data-stu-id="cd119-106">Description</span></span>

<span data-ttu-id="cd119-107">Esta operação implementa um caso especial @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" de, no qual o qubit alvo é conhecido por estar no estado $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="cd119-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="cd119-108">A implementação faz uso e @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" portões.</span><span class="sxs-lookup"><span data-stu-id="cd119-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="cd119-109">A implementação da operação adjacente é otimizada e utiliza a não computação baseada na medição.</span><span class="sxs-lookup"><span data-stu-id="cd119-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="cd119-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="cd119-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="cd119-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cd119-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cd119-112">Mesa da verdade booleana representada como grande inteiro</span><span class="sxs-lookup"><span data-stu-id="cd119-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="cd119-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd119-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cd119-114">Registo de qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="cd119-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cd119-115">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cd119-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cd119-116">Qubit alvo (deve estar em estado de $\ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="cd119-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd119-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd119-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="cd119-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cd119-118">See Also</span></span>

- [<span data-ttu-id="cd119-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="cd119-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)