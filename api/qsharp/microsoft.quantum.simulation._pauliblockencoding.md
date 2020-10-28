---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: função _PauliBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710664"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="663ce-102">função _PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="663ce-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="663ce-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="663ce-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="663ce-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="663ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="663ce-105">Cria uma unidade de codificação de blocos para um Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="663ce-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="663ce-106">O hamiltoniano $H=\sum_{j}\alpha_j P_j$ é descrito por uma soma de termos Pauli $P_j$, cada um com coeficiente real $\alpha_j$.</span><span class="sxs-lookup"><span data-stu-id="663ce-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="663ce-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="663ce-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="663ce-108">sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="663ce-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="663ce-109">Um `GeneratorSystem` que descreve $H$ como uma soma de termos Pauli</span><span class="sxs-lookup"><span data-stu-id="663ce-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a><span data-ttu-id="663ce-110">EstadoPrepUnitário : [Duplo](xref:microsoft.quantum.lang-ref.double)[] -> [Unidade LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="663ce-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="663ce-111">Uma operação unitária $V$ que aplica o $V_j$ unitário controlado no índice $\ket{j}$, dada uma função $f: j\rightarrow V_j$.</span><span class="sxs-lookup"><span data-stu-id="663ce-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="663ce-112">multiplexer :[(Int,](xref:microsoft.quantum.lang-ref.int)[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl) ->[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = unidade> Adj + [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="663ce-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="663ce-113">Saída : ([Duplo,](xref:microsoft.quantum.lang-ref.double)[BlockEncodingReflection)](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="663ce-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="663ce-114">Primeiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="663ce-114">First parameter</span></span>

<span data-ttu-id="663ce-115">A norma única dos coeficientes $\alpha=\sum_{j}[alpha_j</span><span class="sxs-lookup"><span data-stu-id="663ce-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="663ce-116">Segundo parâmetro</span><span class="sxs-lookup"><span data-stu-id="663ce-116">Second parameter</span></span>

<span data-ttu-id="663ce-117">Um `BlockEncodingReflection` $U de dólares unitários do Hamiltonian $U dólares.</span><span class="sxs-lookup"><span data-stu-id="663ce-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="663ce-118">Como este unitário satisfaz $U^2 = I$, é também uma reflexão.</span><span class="sxs-lookup"><span data-stu-id="663ce-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="663ce-119">Observações</span><span class="sxs-lookup"><span data-stu-id="663ce-119">Remarks</span></span>

<span data-ttu-id="663ce-120">Operações de exemplo a preparar e despreparar o estado $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, e construir uma unidade unitária controlada por multiplierinas são <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="663ce-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>