---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: Aplicação Operação DiagonalUnitária
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 8f17c3cb222bef00ead5e7fea5d29d296b9a428a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218857"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="48aa4-102">Aplicação Operação DiagonalUnitária</span><span class="sxs-lookup"><span data-stu-id="48aa4-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="48aa4-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48aa4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48aa4-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48aa4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48aa4-105">Aplica um conjunto de fases complexas aos estados de base numérica de um registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="48aa4-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="48aa4-106">Description</span><span class="sxs-lookup"><span data-stu-id="48aa4-106">Description</span></span>

<span data-ttu-id="48aa4-107">Esta operação implementa uma diagonal unitária que aplica uma fase complexa $e^{i \theta_j}$ no estado do número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="48aa4-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="48aa4-108">Em particular, esta operação pode ser representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="48aa4-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="48aa4-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}i\i\theta_j}\ket{j}bra{j}}</span><span class="sxs-lookup"><span data-stu-id="48aa4-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="48aa4-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="48aa4-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="48aa4-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="48aa4-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="48aa4-112">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="48aa4-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="48aa4-113">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="48aa4-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="48aa4-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="48aa4-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="48aa4-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="48aa4-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="48aa4-116">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="48aa4-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48aa4-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48aa4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="48aa4-118">Observações</span><span class="sxs-lookup"><span data-stu-id="48aa4-118">Remarks</span></span>

<span data-ttu-id="48aa4-119">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="48aa4-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="48aa4-120">Referências</span><span class="sxs-lookup"><span data-stu-id="48aa4-120">References</span></span>

- <span data-ttu-id="48aa4-121">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="48aa4-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="48aa4-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="48aa4-122">See Also</span></span>

- [<span data-ttu-id="48aa4-123">Microsoft.Quantum.Canon.aproximadamenteApplyDiagonalunitary</span><span class="sxs-lookup"><span data-stu-id="48aa4-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)