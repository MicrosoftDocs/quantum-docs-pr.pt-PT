---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Operação AproximadamenteMultiplexZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716796"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="56b7f-102">Operação AproximadamenteMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="56b7f-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="56b7f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56b7f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56b7f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56b7f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56b7f-105">Aplica uma rotação Pauli Z condicionada a uma matriz de qubits, truncando pequenos ângulos de rotação de acordo com uma dada tolerância.</span><span class="sxs-lookup"><span data-stu-id="56b7f-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="56b7f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="56b7f-106">Description</span></span>

<span data-ttu-id="56b7f-107">Isto aplica a operação unitária controlada por multiplicação que executa rotações por ângulo $\theta_j$ sobre o operador pauli de um único qubit $Z$ quando controlado pelo estado do número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="56b7f-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="56b7f-108">Em particular, esta operação pode ser representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="56b7f-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="56b7f-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span><span class="sxs-lookup"><span data-stu-id="56b7f-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="56b7f-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="56b7f-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="56b7f-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="56b7f-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="56b7f-112">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="56b7f-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="56b7f-113">Uma tolerância abaixo da qual pequenos coeficientes são truncados.</span><span class="sxs-lookup"><span data-stu-id="56b7f-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="56b7f-114">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="56b7f-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="56b7f-115">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="56b7f-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="56b7f-116">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="56b7f-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="56b7f-117">controlo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="56b7f-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="56b7f-118">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="56b7f-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="56b7f-119">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="56b7f-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="56b7f-120">Registo de qubit único que é rodado por $e^{i P \theta_j}$.</span><span class="sxs-lookup"><span data-stu-id="56b7f-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56b7f-121">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56b7f-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="56b7f-122">Observações</span><span class="sxs-lookup"><span data-stu-id="56b7f-122">Remarks</span></span>

<span data-ttu-id="56b7f-123">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="56b7f-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="56b7f-124">Referências</span><span class="sxs-lookup"><span data-stu-id="56b7f-124">References</span></span>

- <span data-ttu-id="56b7f-125">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="56b7f-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="56b7f-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="56b7f-126">See Also</span></span>

- [<span data-ttu-id="56b7f-127">Microsoft.Quantum.Canon.MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="56b7f-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)