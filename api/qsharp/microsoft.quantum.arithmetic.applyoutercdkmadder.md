---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Aplicação Operação FuncionarAdder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: acaa563245bb7c701316d2dfd35b5be03d8e024d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843712"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="27545-102">Aplicação Operação FuncionarAdder</span><span class="sxs-lookup"><span data-stu-id="27545-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="27545-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="27545-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="27545-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27545-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27545-105">Operação reversível e in-place que é usada na operação de adição de inteiros RippleCarryAdderCDKM abaixo.</span><span class="sxs-lookup"><span data-stu-id="27545-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="27545-106">Tendo em conta dois registos qubit `xs` e com o mesmo `ys` comprimento, a operação aplica uma sequência de transporte de ondulação de portões CNOT e CCNOT com qubits dentro `xs` e como os `ys` controlos e qubits como `xs` os alvos.</span><span class="sxs-lookup"><span data-stu-id="27545-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="27545-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="27545-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="27545-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27545-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="27545-109">Primeiro registo de qubits, contendo controlos e alvos.</span><span class="sxs-lookup"><span data-stu-id="27545-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="27545-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27545-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="27545-111">Segundo registo de qubits, contribuindo para os controlos.</span><span class="sxs-lookup"><span data-stu-id="27545-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="27545-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27545-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27545-113">O qubit de ancilla usado em RippleCarryAdderCDKM passou para esta operação.</span><span class="sxs-lookup"><span data-stu-id="27545-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27545-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27545-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="27545-115">Referências</span><span class="sxs-lookup"><span data-stu-id="27545-115">References</span></span>

- <span data-ttu-id="27545-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "Um novo circuito de adição de ondas quânticas", 2004.</span><span class="sxs-lookup"><span data-stu-id="27545-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1