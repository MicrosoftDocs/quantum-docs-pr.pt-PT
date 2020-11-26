---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Operação Trotter1ImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1b4e0a9597f4f30b8e92ef91ff0780e7c7ecdc9b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204798"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="54230-102">Operação Trotter1ImplCA</span><span class="sxs-lookup"><span data-stu-id="54230-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="54230-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54230-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54230-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54230-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54230-105">Implementação do integrador Trotter-Suzuki de primeira ordem.</span><span class="sxs-lookup"><span data-stu-id="54230-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="54230-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="54230-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="54230-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="54230-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="54230-108">O número de operações a decompor-se em etapas temporais.</span><span class="sxs-lookup"><span data-stu-id="54230-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="54230-109">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="54230-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="54230-110">Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo) e um registo `Double` quântico `'T` (tipo) para decomposição.</span><span class="sxs-lookup"><span data-stu-id="54230-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="54230-111">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="54230-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="54230-112">Multiplicador no tamanho de cada passo da simulação.</span><span class="sxs-lookup"><span data-stu-id="54230-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="54230-113">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="54230-113">target : 'T</span></span>

<span data-ttu-id="54230-114">Um registo quântico no qual as operações atuam.</span><span class="sxs-lookup"><span data-stu-id="54230-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54230-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54230-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="54230-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="54230-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="54230-117">'T</span><span class="sxs-lookup"><span data-stu-id="54230-117">'T</span></span>

<span data-ttu-id="54230-118">O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .</span><span class="sxs-lookup"><span data-stu-id="54230-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>