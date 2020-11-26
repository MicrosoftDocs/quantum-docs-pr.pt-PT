---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Preparar Operação PrepareUniformSuperposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230094"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="d80f3-102">Preparar Operação PrepareUniformSuperposition</span><span class="sxs-lookup"><span data-stu-id="d80f3-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="d80f3-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d80f3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d80f3-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d80f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d80f3-105">Cria uma superposição uniforme sobre estados que codificam 0 a `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="d80f3-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="d80f3-106">Ou seja, este $U$ unitário cria uma superposição uniforme sobre todos os estados numerais $0$ a $M-1$, dado um estado de entrada $\ket{0\cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="d80f3-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="d80f3-107">Por outras palavras, $$ \begin{align} U\ket {0} =\frac {1} {\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span><span class="sxs-lookup"><span data-stu-id="d80f3-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="d80f3-108">\end{align} $$.</span><span class="sxs-lookup"><span data-stu-id="d80f3-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d80f3-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="d80f3-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="d80f3-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d80f3-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d80f3-111">O número desejado de estados $M$ na sobreposição uniforme.</span><span class="sxs-lookup"><span data-stu-id="d80f3-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="d80f3-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d80f3-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d80f3-113">O registo qubit que armazena o número afirma em `LittleEndian` formato.</span><span class="sxs-lookup"><span data-stu-id="d80f3-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="d80f3-114">Este registo deve ser capaz de armazenar o número $M-1$, e é assumido como inicializado no estado $\ket{0\cdots 0}$.</span><span class="sxs-lookup"><span data-stu-id="d80f3-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d80f3-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d80f3-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d80f3-116">Observações</span><span class="sxs-lookup"><span data-stu-id="d80f3-116">Remarks</span></span>

<span data-ttu-id="d80f3-117">A operação é contígua, mas requer que `indexRegister` esteja numa superposição uniforme sobre os estados de primeira `nIndices` base nesse caso.</span><span class="sxs-lookup"><span data-stu-id="d80f3-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>