---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: Função DeintoTimeStepsCA decomposta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716337"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="53f6a-102">Função DeintoTimeStepsCA decomposta</span><span class="sxs-lookup"><span data-stu-id="53f6a-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="53f6a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53f6a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53f6a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53f6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53f6a-105">Devolve uma operação de implementação do integrador Trotter-Suzuki para uma determinada operação.</span><span class="sxs-lookup"><span data-stu-id="53f6a-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="53f6a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="53f6a-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="53f6a-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53f6a-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53f6a-108">O número de operações a decompor-se em etapas temporais.</span><span class="sxs-lookup"><span data-stu-id="53f6a-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="53f6a-109">op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="53f6a-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="53f6a-110">Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo ) para `Double` decomposição.</span><span class="sxs-lookup"><span data-stu-id="53f6a-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="53f6a-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53f6a-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53f6a-112">Selecione a ordem do integrador Trotter-Suzuki a utilizar.</span><span class="sxs-lookup"><span data-stu-id="53f6a-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="53f6a-113">Encomenda 1 e até encomendas 2, 4, 6,... são atualmente apoiados.</span><span class="sxs-lookup"><span data-stu-id="53f6a-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="53f6a-114">Saída :[(Duplo](xref:microsoft.quantum.lang-ref.double),'T) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="53f6a-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="53f6a-115">Devolve um integrador unitário de implementação do integrador Trotter-Suzuki, onde o primeiro parâmetro `Double` é o tamanho do passo de integração, e o segundo parâmetro é o alvo acionado.</span><span class="sxs-lookup"><span data-stu-id="53f6a-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="53f6a-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="53f6a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="53f6a-117">'T</span><span class="sxs-lookup"><span data-stu-id="53f6a-117">'T</span></span>

<span data-ttu-id="53f6a-118">O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .</span><span class="sxs-lookup"><span data-stu-id="53f6a-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="53f6a-119">Observações</span><span class="sxs-lookup"><span data-stu-id="53f6a-119">Remarks</span></span>

<span data-ttu-id="53f6a-120">Quando chamado com `order` igual a , esta `1` função devolve uma operação que pode ser simulada pelo integrador Trotter-Suzuki de menor ordem $$ \start{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{{{H_j \lambda}, \end{align}08139 e deixe $\lambda$ ser o tempo de evolução (representado pela primeira entrada da operação devolvida), e deixe $ H_j [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) \{ \} _{j = 1}^{m}$ seja o conjunto de geradores dinâmicos (skew-Hermitian) sendo integrados de tal forma que `op(j, lambda, _)` é simulado pelo operador unitário $e^{{H_j \lambda$}</span><span class="sxs-lookup"><span data-stu-id="53f6a-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="53f6a-121">Da mesma forma, um `order` dos `2` retornos do integrador simétrico trotter-Suzuki de segunda ordem $$ \start{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{{{H_k \lambda / 2} \prod_{j' = m}^ {1} e^{H_{j'}</span><span class="sxs-lookup"><span data-stu-id="53f6a-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="53f6a-122">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="53f6a-122">\end{align} $$</span></span>

<span data-ttu-id="53f6a-123">Valores partivos mais `order` elevados são implementados utilizando a construção recursiva de [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="53f6a-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="53f6a-124">Referências</span><span class="sxs-lookup"><span data-stu-id="53f6a-124">References</span></span>

- [<span data-ttu-id="53f6a-125">*D. W. Berry, G. Ahokas, R. Cleve, B.C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="53f6a-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)