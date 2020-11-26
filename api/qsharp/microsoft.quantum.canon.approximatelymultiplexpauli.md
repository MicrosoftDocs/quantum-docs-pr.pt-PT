---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Operação AproximadamenteMultiplexPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 8024df4608f14408bfcd46139e72454ff44b116f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207756"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="7bcb1-102">Operação AproximadamenteMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="7bcb1-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="7bcb1-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7bcb1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7bcb1-105">Aplica uma rotação Pauli condicionada a uma matriz de qubits, truncando pequenos ângulos de rotação de acordo com uma dada tolerância.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7bcb1-106">Description</span><span class="sxs-lookup"><span data-stu-id="7bcb1-106">Description</span></span>

<span data-ttu-id="7bcb1-107">Isto aplica uma operação unitária controlada por multiplique que executa rotações por ângulo $\theta_j$ sobre o operador pauli de um único qubit $P$ quando controlado pelo estado de número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="7bcb1-108">Em particular, a ação desta operação é representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="7bcb1-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="7bcb1-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="7bcb1-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="7bcb1-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="7bcb1-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="7bcb1-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="7bcb1-112">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7bcb1-113">Uma tolerância abaixo da qual pequenos coeficientes são truncados.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="7bcb1-114">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7bcb1-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7bcb1-115">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="7bcb1-116">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="7bcb1-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7bcb1-118">O operador pauli $P$ que determina o eixo de rotação.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="7bcb1-119">controlo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7bcb1-120">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7bcb1-121">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7bcb1-122">Registo de qubit único que é rodado por $e^{i P \theta_j}$.</span><span class="sxs-lookup"><span data-stu-id="7bcb1-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7bcb1-123">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bcb1-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7bcb1-124">Observações</span><span class="sxs-lookup"><span data-stu-id="7bcb1-124">Remarks</span></span>

<span data-ttu-id="7bcb1-125">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="7bcb1-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bcb1-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7bcb1-126">See Also</span></span>

- [<span data-ttu-id="7bcb1-127">Microsoft.Quantum.Canon.MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="7bcb1-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)