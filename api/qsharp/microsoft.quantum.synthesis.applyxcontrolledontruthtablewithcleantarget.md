---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: AplicaXControlledOnTruthTableWithCleanTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725231"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="d3bfd-102">AplicaXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="d3bfd-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="d3bfd-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d3bfd-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d3bfd-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3bfd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3bfd-105">Aplica a @"microsoft.quantum.intrinsic.x" operação em `target` , se a função Boolean `func` avaliar a verdade para a atribuição clássica em `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="d3bfd-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d3bfd-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d3bfd-106">Description</span></span>

<span data-ttu-id="d3bfd-107">Esta operação implementa um caso especial @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" de, no qual o qubit alvo é conhecido por estar no estado $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d3bfd-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="d3bfd-108">A implementação faz uso e @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" portões.</span><span class="sxs-lookup"><span data-stu-id="d3bfd-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="d3bfd-109">A implementação da operação adjacente é otimizada e utiliza a não computação baseada na medição.</span><span class="sxs-lookup"><span data-stu-id="d3bfd-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="d3bfd-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="d3bfd-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="d3bfd-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d3bfd-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d3bfd-112">Mesa da verdade booleana representada como grande inteiro</span><span class="sxs-lookup"><span data-stu-id="d3bfd-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="d3bfd-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d3bfd-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d3bfd-114">Registo de qubits de controlo</span><span class="sxs-lookup"><span data-stu-id="d3bfd-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d3bfd-115">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d3bfd-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d3bfd-116">Qubit alvo (deve estar em estado de $\ket {0} $)</span><span class="sxs-lookup"><span data-stu-id="d3bfd-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3bfd-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3bfd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d3bfd-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d3bfd-118">See Also</span></span>

- [<span data-ttu-id="d3bfd-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span><span class="sxs-lookup"><span data-stu-id="d3bfd-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)