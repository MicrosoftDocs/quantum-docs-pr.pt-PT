---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: AplicaXControlledOnTruthTableWithCleanTarget
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: a54544cd026f26784bb0c41cb12187a8885ed9db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855540"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="4e8b6-102">AplicaXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="4e8b6-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="4e8b6-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="4e8b6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="4e8b6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e8b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e8b6-105">Aplica a @"microsoft.quantum.intrinsic.x" operação em `target` , se a função Boolean `func` avaliar a verdade para a atribuição clássica em `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="4e8b6-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4e8b6-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4e8b6-106">Description</span></span>

<span data-ttu-id="4e8b6-107">Esta operação implementa um caso especial @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" de, no qual o qubit alvo é conhecido por estar no estado $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4e8b6-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="4e8b6-108">A implementação faz uso e @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" portões.</span><span class="sxs-lookup"><span data-stu-id="4e8b6-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="4e8b6-109">A implementação da operação adjacente é otimizada e utiliza a não computação baseada na medição.</span><span class="sxs-lookup"><span data-stu-id="4e8b6-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="4e8b6-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="4e8b6-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="4e8b6-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4e8b6-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4e8b6-112">Mesa da verdade booleana representada como grande inteiro</span><span class="sxs-lookup"><span data-stu-id="4e8b6-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="4e8b6-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4e8b6-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4e8b6-114">Registo de qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="4e8b6-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4e8b6-115">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4e8b6-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4e8b6-116">Qubit alvo (deve estar em estado de $\ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="4e8b6-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e8b6-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e8b6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4e8b6-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4e8b6-118">See Also</span></span>

- [<span data-ttu-id="4e8b6-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="4e8b6-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)