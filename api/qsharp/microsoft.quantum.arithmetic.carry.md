---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operação de transporte
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843362"
---
# <a name="carry-operation"></a><span data-ttu-id="21f25-102">Operação de transporte</span><span class="sxs-lookup"><span data-stu-id="21f25-102">Carry operation</span></span>

<span data-ttu-id="21f25-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="21f25-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="21f25-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21f25-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21f25-105">Implementa um portão de transporte reversível.</span><span class="sxs-lookup"><span data-stu-id="21f25-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="21f25-106">Dado um bit de transporte codificado em qubit `carryIn` e dois bits resumidos `summand1` `summand2` e, calcula o bitwise xor de `carryIn` , e no `summand1` `summand2` qubit e na `summand2` execução é xored para o qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="21f25-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="21f25-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="21f25-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="21f25-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="21f25-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="21f25-109">Qubit de transporte.</span><span class="sxs-lookup"><span data-stu-id="21f25-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="21f25-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="21f25-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="21f25-111">Primeiro resumo e qubit.</span><span class="sxs-lookup"><span data-stu-id="21f25-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="21f25-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="21f25-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="21f25-113">Segundo resumo e qubit, é substituído pela parte inferior da soma de `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="21f25-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="21f25-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="21f25-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="21f25-115">Qubit de execução, será xored com a parte mais alta da soma.</span><span class="sxs-lookup"><span data-stu-id="21f25-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21f25-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21f25-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

