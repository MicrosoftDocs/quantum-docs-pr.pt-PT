---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MedidaSStabilizer Operação deGeradores
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712263"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="32096-102">MedidaSStabilizer Operação deGeradores</span><span class="sxs-lookup"><span data-stu-id="32096-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="32096-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="32096-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="32096-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32096-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32096-105">Mede o conjunto de geradores de um grupo estabilizador.</span><span class="sxs-lookup"><span data-stu-id="32096-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="32096-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="32096-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="32096-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span><span class="sxs-lookup"><span data-stu-id="32096-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="32096-108">Uma variedade de operadores de Pauli multiqubit.</span><span class="sxs-lookup"><span data-stu-id="32096-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="32096-109">Por exemplo, `stabilizerGroup[0]` é uma lista de matrizes Pauli de um único qubit, o produto tensor do qual é um gerador estabilizador.</span><span class="sxs-lookup"><span data-stu-id="32096-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="32096-110">LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="32096-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="32096-111">Uma matriz de qubits onde o código estabilizador é definido.</span><span class="sxs-lookup"><span data-stu-id="32096-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="32096-112">gadget : [(Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __inválidos <Result>__</span><span class="sxs-lookup"><span data-stu-id="32096-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="32096-113">Uma operação que especifica como medir um operador pauli multiqubit.</span><span class="sxs-lookup"><span data-stu-id="32096-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="32096-114">Saída : [Síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="32096-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="32096-115">O resultado das medições.</span><span class="sxs-lookup"><span data-stu-id="32096-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="32096-116">Observações</span><span class="sxs-lookup"><span data-stu-id="32096-116">Remarks</span></span>

<span data-ttu-id="32096-117">Isto não verifica se o conjunto de geradores está a deslocar-se.</span><span class="sxs-lookup"><span data-stu-id="32096-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="32096-118">Se não estiverem a deslocar-se, o resultado das medições pode ser arbitrário.</span><span class="sxs-lookup"><span data-stu-id="32096-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>