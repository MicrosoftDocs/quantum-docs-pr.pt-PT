---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: AplicaInnerTTKAdder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: c822933340d592061eb039af7c6e438212abc265
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843836"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="e899a-102">AplicaInnerTTKAdder</span><span class="sxs-lookup"><span data-stu-id="e899a-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="e899a-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e899a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e899a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e899a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e899a-105">Implementa a função de adição interna para a operação RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="e899a-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="e899a-106">Esta é a operação interna que é conjugada com a operação exterior para construir o adder completo.</span><span class="sxs-lookup"><span data-stu-id="e899a-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e899a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e899a-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e899a-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e899a-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e899a-109">Registo de qubit LittleEndian codificando a primeira entrada e entrada inteiro para RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="e899a-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e899a-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e899a-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e899a-111">Registo de qubit LittleEndian codificando a segunda entrada e entrada inteiro para RippleCarryAdderTTK.</span><span class="sxs-lookup"><span data-stu-id="e899a-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="e899a-112">transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e899a-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e899a-113">O qubit de transporte, é xored com a parte mais significativa da soma.</span><span class="sxs-lookup"><span data-stu-id="e899a-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e899a-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e899a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e899a-115">Observações</span><span class="sxs-lookup"><span data-stu-id="e899a-115">Remarks</span></span>

<span data-ttu-id="e899a-116">A operação controlada especificada faz uso da simetria e cancelamento mútuo de operações para melhorar a implementação padrão que adiciona um controlo a cada operação.</span><span class="sxs-lookup"><span data-stu-id="e899a-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="e899a-117">Referências</span><span class="sxs-lookup"><span data-stu-id="e899a-117">References</span></span>

- <span data-ttu-id="e899a-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="e899a-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530