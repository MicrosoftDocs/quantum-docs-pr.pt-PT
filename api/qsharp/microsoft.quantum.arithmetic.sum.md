---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operação sum
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: 7758e29c9f08f4d05253defbe5a43a5316289522
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221798"
---
# <a name="sum-operation"></a><span data-ttu-id="c86cd-102">Operação sum</span><span class="sxs-lookup"><span data-stu-id="c86cd-102">Sum operation</span></span>

<span data-ttu-id="c86cd-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c86cd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c86cd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c86cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c86cd-105">Implementa um portão de soma reversível.</span><span class="sxs-lookup"><span data-stu-id="c86cd-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="c86cd-106">Dado um bit de transporte codificado em qubit `carryIn` e dois bits resumidos `summand1` `summand2` e, calcula o bitwise xor de `carryIn` , e no `summand1` `summand2` qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="c86cd-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c86cd-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c86cd-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="c86cd-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c86cd-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c86cd-109">Qubit de transporte.</span><span class="sxs-lookup"><span data-stu-id="c86cd-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="c86cd-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c86cd-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c86cd-111">Primeiro resumo e qubit.</span><span class="sxs-lookup"><span data-stu-id="c86cd-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="c86cd-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c86cd-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c86cd-113">Segundo resumo e qubit, é substituído pela parte inferior da soma de `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="c86cd-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c86cd-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c86cd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c86cd-115">Observações</span><span class="sxs-lookup"><span data-stu-id="c86cd-115">Remarks</span></span>

<span data-ttu-id="c86cd-116">Em contraste com a `Carry` operação, isto não calcula a parte de execução.</span><span class="sxs-lookup"><span data-stu-id="c86cd-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>