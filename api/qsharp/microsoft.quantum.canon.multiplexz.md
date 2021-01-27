---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: Operação MultiplexZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: dccfe86104263e23794bce33279e8748f11f5a54
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852434"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="e68e9-102">Operação MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="e68e9-102">MultiplexZ operation</span></span>

<span data-ttu-id="e68e9-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e68e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e68e9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e68e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e68e9-105">Aplica uma rotação Pauli Z condicionada a uma matriz de qubits.</span><span class="sxs-lookup"><span data-stu-id="e68e9-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e68e9-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e68e9-106">Description</span></span>

<span data-ttu-id="e68e9-107">Isto aplica a operação unitária controlada por multiplicação que executa rotações por ângulo $\theta_j$ sobre o operador pauli de um único qubit $Z$ quando controlado pelo estado do número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="e68e9-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="e68e9-108">Em particular, esta operação pode ser representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="e68e9-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="e68e9-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span><span class="sxs-lookup"><span data-stu-id="e68e9-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="e68e9-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="e68e9-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e68e9-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="e68e9-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="e68e9-112">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e68e9-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e68e9-113">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="e68e9-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="e68e9-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="e68e9-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="e68e9-115">controlo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e68e9-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e68e9-116">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="e68e9-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e68e9-117">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e68e9-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e68e9-118">Registo de qubit único que é rodado por $e^{i P \theta_j}$.</span><span class="sxs-lookup"><span data-stu-id="e68e9-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e68e9-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e68e9-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e68e9-120">Observações</span><span class="sxs-lookup"><span data-stu-id="e68e9-120">Remarks</span></span>

<span data-ttu-id="e68e9-121">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="e68e9-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="e68e9-122">Referências</span><span class="sxs-lookup"><span data-stu-id="e68e9-122">References</span></span>

- <span data-ttu-id="e68e9-123">Síntese dos Circuitos Quânticos Da Lógica Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="e68e9-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="e68e9-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e68e9-124">See Also</span></span>

- [<span data-ttu-id="e68e9-125">Microsoft.Quantum.Canon.AproximadamenteMultiplexZ</span><span class="sxs-lookup"><span data-stu-id="e68e9-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)