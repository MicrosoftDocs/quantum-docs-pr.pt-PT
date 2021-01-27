---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operação Trotter2ImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852025"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="5a0f4-102">Operação Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="5a0f4-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="5a0f4-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a0f4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a0f4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a0f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a0f4-105">Implementação do integrador Trotter-Suzuki de segunda ordem.</span><span class="sxs-lookup"><span data-stu-id="5a0f4-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a0f4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5a0f4-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="5a0f4-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a0f4-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5a0f4-108">O número de operações a decompor-se em etapas temporais.</span><span class="sxs-lookup"><span data-stu-id="5a0f4-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="5a0f4-109">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="5a0f4-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5a0f4-110">Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo) e um registo `Double` quântico `'T` (tipo) para decomposição.</span><span class="sxs-lookup"><span data-stu-id="5a0f4-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5a0f4-111">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5a0f4-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5a0f4-112">Multiplicador no tamanho de cada passo da simulação.</span><span class="sxs-lookup"><span data-stu-id="5a0f4-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="5a0f4-113">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="5a0f4-113">target : 'T</span></span>

<span data-ttu-id="5a0f4-114">Um registo quântico no qual as operações atuam.</span><span class="sxs-lookup"><span data-stu-id="5a0f4-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a0f4-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a0f4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5a0f4-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5a0f4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a0f4-117">'T</span><span class="sxs-lookup"><span data-stu-id="5a0f4-117">'T</span></span>

<span data-ttu-id="5a0f4-118">O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .</span><span class="sxs-lookup"><span data-stu-id="5a0f4-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="5a0f4-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5a0f4-119">Example</span></span>

<span data-ttu-id="5a0f4-120">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="5a0f4-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

<span data-ttu-id="5a0f4-121">e</span><span class="sxs-lookup"><span data-stu-id="5a0f4-121">and</span></span>

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```