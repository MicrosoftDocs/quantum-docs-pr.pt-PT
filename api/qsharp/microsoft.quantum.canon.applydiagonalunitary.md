---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: Aplicação Operação DiagonalUnitária
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718283"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="70b77-102">Aplicação Operação DiagonalUnitária</span><span class="sxs-lookup"><span data-stu-id="70b77-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="70b77-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70b77-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70b77-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70b77-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70b77-105">Aplica um conjunto de fases complexas aos estados de base numérica de um registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="70b77-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="70b77-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="70b77-106">Description</span></span>

<span data-ttu-id="70b77-107">Esta operação implementa uma diagonal unitária que aplica uma fase complexa $e^{i \theta_j}$ no estado do número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="70b77-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="70b77-108">Em particular, esta operação pode ser representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="70b77-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="70b77-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}i\i\theta_j}\ket{j}bra{j}}</span><span class="sxs-lookup"><span data-stu-id="70b77-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="70b77-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="70b77-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="70b77-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="70b77-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="70b77-112">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="70b77-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="70b77-113">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="70b77-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="70b77-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="70b77-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="70b77-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="70b77-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="70b77-116">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="70b77-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70b77-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70b77-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="70b77-118">Observações</span><span class="sxs-lookup"><span data-stu-id="70b77-118">Remarks</span></span>

<span data-ttu-id="70b77-119">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="70b77-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="70b77-120">Referências</span><span class="sxs-lookup"><span data-stu-id="70b77-120">References</span></span>

- <span data-ttu-id="70b77-121">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="70b77-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="70b77-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="70b77-122">See Also</span></span>

- [<span data-ttu-id="70b77-123">Microsoft.Quantum.Canon.aproximadamenteApplyDiagonalunitary</span><span class="sxs-lookup"><span data-stu-id="70b77-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)