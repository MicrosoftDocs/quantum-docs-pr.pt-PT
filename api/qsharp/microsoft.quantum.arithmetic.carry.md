---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operação de transporte
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223600"
---
# <a name="carry-operation"></a><span data-ttu-id="747ca-102">Operação de transporte</span><span class="sxs-lookup"><span data-stu-id="747ca-102">Carry operation</span></span>

<span data-ttu-id="747ca-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="747ca-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="747ca-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="747ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="747ca-105">Implementa um portão de transporte reversível.</span><span class="sxs-lookup"><span data-stu-id="747ca-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="747ca-106">Dado um bit de transporte codificado em qubit `carryIn` e dois bits resumidos `summand1` `summand2` e, calcula o bitwise xor de `carryIn` , e no `summand1` `summand2` qubit e na `summand2` execução é xored para o qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="747ca-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="747ca-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="747ca-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="747ca-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="747ca-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="747ca-109">Qubit de transporte.</span><span class="sxs-lookup"><span data-stu-id="747ca-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="747ca-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="747ca-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="747ca-111">Primeiro resumo e qubit.</span><span class="sxs-lookup"><span data-stu-id="747ca-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="747ca-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="747ca-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="747ca-113">Segundo resumo e qubit, é substituído pela parte inferior da soma de `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="747ca-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="747ca-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="747ca-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="747ca-115">Qubit de execução, será xored com a parte mais alta da soma.</span><span class="sxs-lookup"><span data-stu-id="747ca-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="747ca-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="747ca-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

