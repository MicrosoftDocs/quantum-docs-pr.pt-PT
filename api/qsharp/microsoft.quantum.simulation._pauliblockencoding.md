---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: função _PauliBlockEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: c27ef1a6b7cd7c84defe2a783e9fb1610e52d1e7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851071"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="63d40-102">função _PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="63d40-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="63d40-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="63d40-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="63d40-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63d40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63d40-105">Cria uma unidade de codificação de blocos para um Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="63d40-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="63d40-106">O hamiltoniano $H=\sum_{j}\alpha_j P_j$ é descrito por uma soma de termos Pauli $P_j$, cada um com coeficiente real $\alpha_j$.</span><span class="sxs-lookup"><span data-stu-id="63d40-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="63d40-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="63d40-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="63d40-108">sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="63d40-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="63d40-109">Um `GeneratorSystem` que descreve $H$ como uma soma de termos Pauli</span><span class="sxs-lookup"><span data-stu-id="63d40-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a><span data-ttu-id="63d40-110">EstadoPrepUnitário : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="63d40-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="63d40-111">Uma operação unitária $V$ que aplica o $V_j$ unitário controlado no índice $\ket{j}$, dada uma função $f: j\rightarrow V_j$.</span><span class="sxs-lookup"><span data-stu-id="63d40-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="63d40-112">multiplexer :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit) is Adj + Ctl) ->[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [unidade](xref:microsoft.quantum.lang-ref.unit)> é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="63d40-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="63d40-113">Saída : ([Duplo,](xref:microsoft.quantum.lang-ref.double)[BlockEncodingReflection)](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="63d40-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="63d40-114">Primeiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="63d40-114">First parameter</span></span>

<span data-ttu-id="63d40-115">A norma única dos coeficientes $\alpha=\sum_{j}|\alpha_j|$.</span><span class="sxs-lookup"><span data-stu-id="63d40-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="63d40-116">Segundo parâmetro</span><span class="sxs-lookup"><span data-stu-id="63d40-116">Second parameter</span></span>

<span data-ttu-id="63d40-117">Um `BlockEncodingReflection` $U de dólares unitários do Hamiltonian $U dólares.</span><span class="sxs-lookup"><span data-stu-id="63d40-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="63d40-118">Como este unitário satisfaz $U^2 = I$, é também uma reflexão.</span><span class="sxs-lookup"><span data-stu-id="63d40-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="63d40-119">Observações</span><span class="sxs-lookup"><span data-stu-id="63d40-119">Remarks</span></span>

<span data-ttu-id="63d40-120">Operações de exemplo a preparar e despreparar o estado $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, e construir uma unidade unitária controlada por multiplierinas são <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="63d40-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>