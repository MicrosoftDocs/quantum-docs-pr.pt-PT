---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: função _DeltaParityCNOTbitstring
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710849"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="dcb0e-102">função _DeltaParityCNOTbitstring</span><span class="sxs-lookup"><span data-stu-id="dcb0e-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="dcb0e-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="dcb0e-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="dcb0e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dcb0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dcb0e-105">Passo de processamento clássico de `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="dcb0e-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="dcb0e-106">Isto calcula uma lista de qubits de controlo para avaliar a diferença de paridade entre dois PQRS... termos de mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="dcb0e-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="dcb0e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="dcb0e-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="dcb0e-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dcb0e-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="dcb0e-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dcb0e-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="dcb0e-110">Saída :[(Int,](xref:microsoft.quantum.lang-ref.int)[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="dcb0e-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="dcb0e-111">Observações</span><span class="sxs-lookup"><span data-stu-id="dcb0e-111">Remarks</span></span>

<span data-ttu-id="dcb0e-112">Isto pressupõe que a duração dos termos é par.</span><span class="sxs-lookup"><span data-stu-id="dcb0e-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="dcb0e-113">Lista de controlos de cálculo para diferença de paridade entre dois termos.</span><span class="sxs-lookup"><span data-stu-id="dcb0e-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="dcb0e-114">Isto pressupõe que as listas de entradas estão ordenadas por ordem ascendente.</span><span class="sxs-lookup"><span data-stu-id="dcb0e-114">This assumes that the input lists is sorted in ascending order.</span></span>