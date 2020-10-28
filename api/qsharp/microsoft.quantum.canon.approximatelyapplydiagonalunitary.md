---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: Operação aproximadamenteApplyDiagonalUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716824"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="a5d3c-102">Operação aproximadamenteApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="a5d3c-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="a5d3c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5d3c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5d3c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5d3c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5d3c-105">Aplica um conjunto de fases complexas aos estados de base numérica de um registo de qubits, truncando pequenos ângulos de rotação de acordo com uma dada tolerância.</span><span class="sxs-lookup"><span data-stu-id="a5d3c-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="a5d3c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5d3c-106">Description</span></span>

<span data-ttu-id="a5d3c-107">Esta operação implementa uma diagonal unitária que aplica uma fase complexa $e^{i \theta_j}$ no estado do número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="a5d3c-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="a5d3c-108">Em particular, esta operação pode ser representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="a5d3c-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="a5d3c-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}i\i\theta_j}\ket{j}bra{j}}</span><span class="sxs-lookup"><span data-stu-id="a5d3c-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="a5d3c-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="a5d3c-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="a5d3c-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="a5d3c-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="a5d3c-112">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a5d3c-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a5d3c-113">Uma tolerância abaixo da qual pequenos coeficientes são truncados.</span><span class="sxs-lookup"><span data-stu-id="a5d3c-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="a5d3c-114">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a5d3c-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a5d3c-115">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="a5d3c-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="a5d3c-116">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="a5d3c-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="a5d3c-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a5d3c-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a5d3c-118">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="a5d3c-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5d3c-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5d3c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a5d3c-120">Observações</span><span class="sxs-lookup"><span data-stu-id="a5d3c-120">Remarks</span></span>

<span data-ttu-id="a5d3c-121">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="a5d3c-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="a5d3c-122">Referências</span><span class="sxs-lookup"><span data-stu-id="a5d3c-122">References</span></span>

- <span data-ttu-id="a5d3c-123">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="a5d3c-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="a5d3c-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a5d3c-124">See Also</span></span>

- [<span data-ttu-id="a5d3c-125">Microsoft.Quantum.Canon.ApplyDiagonalunitary</span><span class="sxs-lookup"><span data-stu-id="a5d3c-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)