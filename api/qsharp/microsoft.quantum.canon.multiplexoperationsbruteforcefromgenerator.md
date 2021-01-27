---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Operação MultiplexOperationsBruteForceFromGenerator
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 395102c7ffffa81d1a9b6cbf29c9cc22fae6057e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852507"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="707c8-102">Operação MultiplexOperationsBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="707c8-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="707c8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="707c8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="707c8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="707c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="707c8-105">Aplica uma operação unitária controlada por multiplicões $U$ que aplica uma $V_j$ unitária quando controlada pelo estado do número n-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="707c8-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="707c8-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span><span class="sxs-lookup"><span data-stu-id="707c8-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="707c8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="707c8-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="707c8-108">unitárioGenerator :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span><span class="sxs-lookup"><span data-stu-id="707c8-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="707c8-109">Um tuple onde o primeiro elemento `Int` é o número de unitários $N$, e o segundo elemento é uma `(Int -> ('T => () is Adj + Ctl))` função que leva um inteiro $j$ em $[0,N-1]$ e produz a operação unitária $V_j$.</span><span class="sxs-lookup"><span data-stu-id="707c8-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="707c8-110">índice : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="707c8-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="707c8-111">$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.</span><span class="sxs-lookup"><span data-stu-id="707c8-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="707c8-112">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="707c8-112">target : 'T</span></span>

<span data-ttu-id="707c8-113">Registo genérico de qubit que $V_j$ atua.</span><span class="sxs-lookup"><span data-stu-id="707c8-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="707c8-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="707c8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="707c8-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="707c8-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="707c8-116">'T</span><span class="sxs-lookup"><span data-stu-id="707c8-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="707c8-117">Observações</span><span class="sxs-lookup"><span data-stu-id="707c8-117">Remarks</span></span>

<span data-ttu-id="707c8-118">`coefficients` serão acolchoados com elementos de identidade se forem especificados menos de $2^n$ .</span><span class="sxs-lookup"><span data-stu-id="707c8-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="707c8-119">Esta versão é implementada diretamente através de operadores unitários controlados por n.</span><span class="sxs-lookup"><span data-stu-id="707c8-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>