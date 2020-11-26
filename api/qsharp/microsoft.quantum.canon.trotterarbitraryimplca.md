---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Operação TrotterArbitraryImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 2abfbb9d51a98d8ede1b0835875a3771ffda0691
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204730"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="270c4-102">Operação TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="270c4-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="270c4-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="270c4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="270c4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="270c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="270c4-105">Implementação recursiva do integrador Trotter-Suzuki de encomenda.</span><span class="sxs-lookup"><span data-stu-id="270c4-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="270c4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="270c4-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="270c4-107">ordem : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="270c4-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="270c4-108">Ordem do integrador Trotter-Suzuki.</span><span class="sxs-lookup"><span data-stu-id="270c4-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="270c4-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="270c4-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="270c4-110">O número de operações a decompor-se em etapas temporais.</span><span class="sxs-lookup"><span data-stu-id="270c4-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="270c4-111">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="270c4-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="270c4-112">Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo) e um registo `Double` quântico `'T` (tipo) para decomposição.</span><span class="sxs-lookup"><span data-stu-id="270c4-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="270c4-113">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="270c4-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="270c4-114">Multiplicador no tamanho de cada passo da simulação.</span><span class="sxs-lookup"><span data-stu-id="270c4-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="270c4-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="270c4-115">target : 'T</span></span>

<span data-ttu-id="270c4-116">Um registo quântico no qual as operações atuam.</span><span class="sxs-lookup"><span data-stu-id="270c4-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="270c4-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="270c4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="270c4-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="270c4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="270c4-119">'T</span><span class="sxs-lookup"><span data-stu-id="270c4-119">'T</span></span>

<span data-ttu-id="270c4-120">O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .</span><span class="sxs-lookup"><span data-stu-id="270c4-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>