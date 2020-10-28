---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Operação RippleCarryAdderD
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719590"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="0f151-102">Operação RippleCarryAdderD</span><span class="sxs-lookup"><span data-stu-id="0f151-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="0f151-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0f151-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0f151-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f151-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f151-105">Reversível, adição de dois inteiros.</span><span class="sxs-lookup"><span data-stu-id="0f151-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="0f151-106">Tendo em conta dois inteiros $n de $-bit codificados nos registos de LittleEndian `xs` e , e um transporte `ys` qubit, a operação calcula a soma dos dois inteiros onde os $n$ menos significativos do resultado são mantidos `ys` e a broca de execução é recortada ao qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="0f151-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0f151-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0f151-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="0f151-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f151-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f151-109">Registo de qubit littleEndian codificando o primeiro resumo inteiro.</span><span class="sxs-lookup"><span data-stu-id="0f151-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="0f151-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f151-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f151-111">O registo de qubits LittleEndian codificando o segundo resumo inteiro, é modificado para manter o $n$ menos significativo da soma.</span><span class="sxs-lookup"><span data-stu-id="0f151-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="0f151-112">transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0f151-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0f151-113">O qubit de transporte, é xored com a parte mais significativa da soma.</span><span class="sxs-lookup"><span data-stu-id="0f151-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f151-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f151-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0f151-115">Observações</span><span class="sxs-lookup"><span data-stu-id="0f151-115">Remarks</span></span>

<span data-ttu-id="0f151-116">A operação controlada especificada faz uso da simetria e cancelamento mútuo de operações para melhorar a implementação padrão que adiciona um controlo a cada operação.</span><span class="sxs-lookup"><span data-stu-id="0f151-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="0f151-117">Referências</span><span class="sxs-lookup"><span data-stu-id="0f151-117">References</span></span>

- <span data-ttu-id="0f151-118">Thomas G. Draper: "Adição num Computador Quântico", 2000.</span><span class="sxs-lookup"><span data-stu-id="0f151-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033