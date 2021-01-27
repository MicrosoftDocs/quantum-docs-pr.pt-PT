---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Operação MultiplexPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 656b510cb19af69a9a3f0d537d54b0abfe76de4b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852453"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="61f60-102">Operação MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="61f60-102">MultiplexPauli operation</span></span>

<span data-ttu-id="61f60-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61f60-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61f60-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61f60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61f60-105">Aplica uma rotação Pauli condicionada a uma matriz de qubits.</span><span class="sxs-lookup"><span data-stu-id="61f60-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="61f60-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="61f60-106">Description</span></span>

<span data-ttu-id="61f60-107">Isto aplica uma operação unitária controlada por multiplique que executa rotações por ângulo $\theta_j$ sobre o operador pauli de um único qubit $P$ quando controlado pelo estado de número de $n$-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="61f60-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="61f60-108">Em particular, a ação desta operação é representada pelo unitário</span><span class="sxs-lookup"><span data-stu-id="61f60-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="61f60-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span><span class="sxs-lookup"><span data-stu-id="61f60-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="61f60-110">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="61f60-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="61f60-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="61f60-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="61f60-112">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="61f60-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="61f60-113">Matriz de até $2^n$ coeficientes $\theta_j$.</span><span class="sxs-lookup"><span data-stu-id="61f60-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="61f60-114">O coeficiente de $j$th indexa o estado numérico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="61f60-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="61f60-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="61f60-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="61f60-116">O operador pauli $P$ que determina o eixo de rotação.</span><span class="sxs-lookup"><span data-stu-id="61f60-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="61f60-117">controlo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="61f60-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="61f60-118">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="61f60-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="61f60-119">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="61f60-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="61f60-120">Registo de qubit único que é rodado por $e^{i P \theta_j}$.</span><span class="sxs-lookup"><span data-stu-id="61f60-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61f60-121">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61f60-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="61f60-122">Observações</span><span class="sxs-lookup"><span data-stu-id="61f60-122">Remarks</span></span>

<span data-ttu-id="61f60-123">`coefficients` serão acolchoados com elementos $\theta_j = 0,0$ se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="61f60-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="61f60-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="61f60-124">See Also</span></span>

- [<span data-ttu-id="61f60-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="61f60-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)