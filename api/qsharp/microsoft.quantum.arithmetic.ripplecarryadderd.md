---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Operação RippleCarryAdderD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: f0f6f39fbff9f682f8f74a982c0a41847df1397a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842971"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="db932-102">Operação RippleCarryAdderD</span><span class="sxs-lookup"><span data-stu-id="db932-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="db932-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="db932-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="db932-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db932-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db932-105">Reversível, adição de dois inteiros.</span><span class="sxs-lookup"><span data-stu-id="db932-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="db932-106">Tendo em conta dois inteiros $n de $-bit codificados nos registos de LittleEndian `xs` e , e um transporte `ys` qubit, a operação calcula a soma dos dois inteiros onde os $n$ menos significativos do resultado são mantidos `ys` e a broca de execução é recortada ao qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="db932-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="db932-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="db932-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="db932-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db932-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db932-109">Registo de qubit littleEndian codificando o primeiro resumo inteiro.</span><span class="sxs-lookup"><span data-stu-id="db932-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="db932-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db932-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db932-111">O registo de qubits LittleEndian codificando o segundo resumo inteiro, é modificado para manter o $n$ menos significativo da soma.</span><span class="sxs-lookup"><span data-stu-id="db932-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="db932-112">transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="db932-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="db932-113">O qubit de transporte, é xored com a parte mais significativa da soma.</span><span class="sxs-lookup"><span data-stu-id="db932-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db932-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db932-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="db932-115">Observações</span><span class="sxs-lookup"><span data-stu-id="db932-115">Remarks</span></span>

<span data-ttu-id="db932-116">A operação controlada especificada faz uso da simetria e cancelamento mútuo de operações para melhorar a implementação padrão que adiciona um controlo a cada operação.</span><span class="sxs-lookup"><span data-stu-id="db932-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="db932-117">Referências</span><span class="sxs-lookup"><span data-stu-id="db932-117">References</span></span>

- <span data-ttu-id="db932-118">Thomas G. Draper: "Adição num Computador Quântico", 2000.</span><span class="sxs-lookup"><span data-stu-id="db932-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033