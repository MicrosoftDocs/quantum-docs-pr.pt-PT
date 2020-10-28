---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Operação RippleCarryAdderTTK
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719566"
---
# <a name="ripplecarryadderttk-operation"></a><span data-ttu-id="aa144-102">Operação RippleCarryAdderTTK</span><span class="sxs-lookup"><span data-stu-id="aa144-102">RippleCarryAdderTTK operation</span></span>

<span data-ttu-id="aa144-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aa144-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aa144-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa144-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa144-105">Reversível, adição de dois inteiros.</span><span class="sxs-lookup"><span data-stu-id="aa144-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="aa144-106">Tendo em conta dois inteiros $n de $-bit codificados nos registos de LittleEndian `xs` e , e um transporte `ys` qubit, a operação calcula a soma dos dois inteiros onde os $n$ menos significativos do resultado são mantidos `ys` e a broca de execução é recortada ao qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="aa144-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="aa144-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="aa144-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="aa144-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa144-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa144-109">Registo de qubit littleEndian codificando o primeiro resumo inteiro.</span><span class="sxs-lookup"><span data-stu-id="aa144-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="aa144-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aa144-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aa144-111">O registo de qubits LittleEndian codificando o segundo resumo inteiro, é modificado para manter o $n$ menos significativo da soma.</span><span class="sxs-lookup"><span data-stu-id="aa144-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="aa144-112">transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aa144-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aa144-113">O qubit de transporte, é xored com a parte mais significativa da soma.</span><span class="sxs-lookup"><span data-stu-id="aa144-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa144-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa144-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa144-115">Observações</span><span class="sxs-lookup"><span data-stu-id="aa144-115">Remarks</span></span>

<span data-ttu-id="aa144-116">Esta operação tem a mesma funcionalidade que o RippleCarryAdderD e, RippleCarryAdderCDKM, mas não utiliza qubits de oscilação.</span><span class="sxs-lookup"><span data-stu-id="aa144-116">This operation has the same functionality as RippleCarryAdderD and, RippleCarryAdderCDKM but does not use any ancilla qubits.</span></span>

## <a name="references"></a><span data-ttu-id="aa144-117">Referências</span><span class="sxs-lookup"><span data-stu-id="aa144-117">References</span></span>

- <span data-ttu-id="aa144-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="aa144-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530