---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operação sum
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847760"
---
# <a name="sum-operation"></a><span data-ttu-id="743ca-102">Operação sum</span><span class="sxs-lookup"><span data-stu-id="743ca-102">Sum operation</span></span>

<span data-ttu-id="743ca-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="743ca-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="743ca-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="743ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="743ca-105">Implementa um portão de soma reversível.</span><span class="sxs-lookup"><span data-stu-id="743ca-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="743ca-106">Dado um bit de transporte codificado em qubit `carryIn` e dois bits resumidos `summand1` `summand2` e, calcula o bitwise xor de `carryIn` , e no `summand1` `summand2` qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="743ca-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="743ca-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="743ca-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="743ca-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="743ca-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="743ca-109">Qubit de transporte.</span><span class="sxs-lookup"><span data-stu-id="743ca-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="743ca-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="743ca-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="743ca-111">Primeiro resumo e qubit.</span><span class="sxs-lookup"><span data-stu-id="743ca-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="743ca-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="743ca-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="743ca-113">Segundo resumo e qubit, é substituído pela parte inferior da soma de `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="743ca-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="743ca-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="743ca-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="743ca-115">Observações</span><span class="sxs-lookup"><span data-stu-id="743ca-115">Remarks</span></span>

<span data-ttu-id="743ca-116">Em contraste com a `Carry` operação, isto não calcula a parte de execução.</span><span class="sxs-lookup"><span data-stu-id="743ca-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>