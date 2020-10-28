---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Operação Trotter1ImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 250b80729530a5d3054e037d9dd653904a57f6d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715301"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="c1db6-102">Operação Trotter1ImplCA</span><span class="sxs-lookup"><span data-stu-id="c1db6-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="c1db6-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1db6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1db6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1db6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1db6-105">Implementação do integrador Trotter-Suzuki de primeira ordem.</span><span class="sxs-lookup"><span data-stu-id="c1db6-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="c1db6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1db6-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="c1db6-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1db6-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1db6-108">O número de operações a decompor-se em etapas temporais.</span><span class="sxs-lookup"><span data-stu-id="c1db6-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="c1db6-109">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="c1db6-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c1db6-110">Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo) e um registo `Double` quântico `'T` (tipo) para decomposição.</span><span class="sxs-lookup"><span data-stu-id="c1db6-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c1db6-111">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1db6-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c1db6-112">Multiplicador no tamanho de cada passo da simulação.</span><span class="sxs-lookup"><span data-stu-id="c1db6-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="c1db6-113">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="c1db6-113">target : 'T</span></span>

<span data-ttu-id="c1db6-114">Um registo quântico no qual as operações atuam.</span><span class="sxs-lookup"><span data-stu-id="c1db6-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1db6-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1db6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c1db6-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c1db6-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c1db6-117">'T</span><span class="sxs-lookup"><span data-stu-id="c1db6-117">'T</span></span>

<span data-ttu-id="c1db6-118">O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .</span><span class="sxs-lookup"><span data-stu-id="c1db6-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>