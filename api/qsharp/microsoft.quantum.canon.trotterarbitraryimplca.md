---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Operação TrotterArbitraryImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715287"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="1fe5d-102">Operação TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="1fe5d-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="1fe5d-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1fe5d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1fe5d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1fe5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1fe5d-105">Implementação recursiva do integrador Trotter-Suzuki de encomenda.</span><span class="sxs-lookup"><span data-stu-id="1fe5d-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="1fe5d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1fe5d-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="1fe5d-107">ordem : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fe5d-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fe5d-108">Ordem do integrador Trotter-Suzuki.</span><span class="sxs-lookup"><span data-stu-id="1fe5d-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="1fe5d-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fe5d-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fe5d-110">O número de operações a decompor-se em etapas temporais.</span><span class="sxs-lookup"><span data-stu-id="1fe5d-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="1fe5d-111">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="1fe5d-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1fe5d-112">Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo) e um registo `Double` quântico `'T` (tipo) para decomposição.</span><span class="sxs-lookup"><span data-stu-id="1fe5d-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="1fe5d-113">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1fe5d-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1fe5d-114">Multiplicador no tamanho de cada passo da simulação.</span><span class="sxs-lookup"><span data-stu-id="1fe5d-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="1fe5d-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="1fe5d-115">target : 'T</span></span>

<span data-ttu-id="1fe5d-116">Um registo quântico no qual as operações atuam.</span><span class="sxs-lookup"><span data-stu-id="1fe5d-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1fe5d-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1fe5d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1fe5d-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="1fe5d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1fe5d-119">'T</span><span class="sxs-lookup"><span data-stu-id="1fe5d-119">'T</span></span>

<span data-ttu-id="1fe5d-120">O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .</span><span class="sxs-lookup"><span data-stu-id="1fe5d-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>