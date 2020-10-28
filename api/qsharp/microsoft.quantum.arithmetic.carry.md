---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operação de transporte
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721307"
---
# <a name="carry-operation"></a><span data-ttu-id="f9423-102">Operação de transporte</span><span class="sxs-lookup"><span data-stu-id="f9423-102">Carry operation</span></span>

<span data-ttu-id="f9423-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f9423-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f9423-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9423-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9423-105">Implementa um portão de transporte reversível.</span><span class="sxs-lookup"><span data-stu-id="f9423-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="f9423-106">Dado um bit de transporte codificado em qubit `carryIn` e dois bits resumidos `summand1` `summand2` e, calcula o bitwise xor de `carryIn` , e no `summand1` `summand2` qubit e na `summand2` execução é xored para o qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="f9423-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f9423-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f9423-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="f9423-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f9423-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f9423-109">Qubit de transporte.</span><span class="sxs-lookup"><span data-stu-id="f9423-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="f9423-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f9423-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f9423-111">Primeiro resumo e qubit.</span><span class="sxs-lookup"><span data-stu-id="f9423-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="f9423-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f9423-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f9423-113">Segundo resumo e qubit, é substituído pela parte inferior da soma de `summand1` e `summand2` .</span><span class="sxs-lookup"><span data-stu-id="f9423-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="f9423-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f9423-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f9423-115">Qubit de execução, será xored com a parte mais alta da soma.</span><span class="sxs-lookup"><span data-stu-id="f9423-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9423-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9423-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

