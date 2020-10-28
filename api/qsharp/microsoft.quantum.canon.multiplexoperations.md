---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operação MultiplexOperations
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715833"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="7819b-102">Operação MultiplexOperations</span><span class="sxs-lookup"><span data-stu-id="7819b-102">MultiplexOperations operation</span></span>

<span data-ttu-id="7819b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7819b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7819b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7819b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7819b-105">Aplica uma série de operações controladas por uma série de estados numerais.</span><span class="sxs-lookup"><span data-stu-id="7819b-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="7819b-106">Ou seja, aplica operação unitária controlada pela Multiplicação $U$ que aplica um $V_j$ unitário quando controlado por $n estado do número de qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="7819b-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="7819b-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span><span class="sxs-lookup"><span data-stu-id="7819b-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="7819b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7819b-108">Input</span></span>

### <a name="unitaries--t--unit-adj--ctl"></a><span data-ttu-id="7819b-109">unitários : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + CTL[]</span><span class="sxs-lookup"><span data-stu-id="7819b-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="7819b-110">Matriz de até $2^n$ operações unitárias.</span><span class="sxs-lookup"><span data-stu-id="7819b-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="7819b-111">A operação de $j$th é indexada pelo estado numémico $\ket{j}$ codificado em formato pequeno-endiano.</span><span class="sxs-lookup"><span data-stu-id="7819b-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="7819b-112">índice : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7819b-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7819b-113">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="7819b-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="7819b-114">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="7819b-114">target : 'T</span></span>

<span data-ttu-id="7819b-115">Registo genérico de qubit que $V_j$ atua.</span><span class="sxs-lookup"><span data-stu-id="7819b-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7819b-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7819b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7819b-117">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7819b-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7819b-118">'T</span><span class="sxs-lookup"><span data-stu-id="7819b-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="7819b-119">Observações</span><span class="sxs-lookup"><span data-stu-id="7819b-119">Remarks</span></span>

<span data-ttu-id="7819b-120">`coefficients` serão acolchoados com elementos de identidade se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="7819b-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="7819b-121">Esta implementação utiliza $n - 1$ qubits auxiliares.</span><span class="sxs-lookup"><span data-stu-id="7819b-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="7819b-122">Referências</span><span class="sxs-lookup"><span data-stu-id="7819b-122">References</span></span>

- <span data-ttu-id="7819b-123">Para a primeira simulação quântica com velocidade quântica Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="7819b-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>