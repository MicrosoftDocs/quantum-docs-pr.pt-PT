---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Operação AproximadamenteMultiplexPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: c91937d9e82a2a1514d81529adb35a5f804a0e13
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716813"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="06c39-102">Operação AproximadamenteMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="06c39-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="06c39-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06c39-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06c39-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06c39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06c39-105">Aplica uma rotação Pauli condicionada a uma matriz de qubits, truncando pequenos ângulos de rotação de acordo com uma dada tolerância.</span><span class="sxs-lookup"><span data-stu-id="06c39-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="06c39-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="06c39-106">Description</span></span>

<span data-ttu-id="06c39-107">Isto aplica uma operação unitária controlada por multiplique que executa rotações por ângulo $\theta_j$ sobre o operador pauli de um único qubit $P$ quando controlado pelo estado de número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="06c39-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="06c39-108">Em particular, a ação desta operação é representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="06c39-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="06c39-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span><span class="sxs-lookup"><span data-stu-id="06c39-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="06c39-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="06c39-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="06c39-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="06c39-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="06c39-112">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06c39-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06c39-113">Uma tolerância abaixo da qual pequenos coeficientes são truncados.</span><span class="sxs-lookup"><span data-stu-id="06c39-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="06c39-114">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="06c39-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="06c39-115">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="06c39-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="06c39-116">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="06c39-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="06c39-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="06c39-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="06c39-118">O operador pauli $P$ que determina o eixo de rotação.</span><span class="sxs-lookup"><span data-stu-id="06c39-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="06c39-119">controlo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06c39-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="06c39-120">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="06c39-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="06c39-121">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="06c39-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="06c39-122">Registo de qubit único que é rodado por $e^{i P \theta_j}$.</span><span class="sxs-lookup"><span data-stu-id="06c39-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06c39-123">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06c39-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="06c39-124">Observações</span><span class="sxs-lookup"><span data-stu-id="06c39-124">Remarks</span></span>

<span data-ttu-id="06c39-125">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="06c39-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="06c39-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="06c39-126">See Also</span></span>

- [<span data-ttu-id="06c39-127">Microsoft.Quantum.Canon.MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="06c39-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)