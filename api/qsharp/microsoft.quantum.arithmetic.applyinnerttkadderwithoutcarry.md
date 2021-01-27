---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 0c1626c788215181b5ed45dc98bed928b5e4848a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843814"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="57176-102">ApplyInnerTTKAdderWithoutCarry operação</span><span class="sxs-lookup"><span data-stu-id="57176-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="57176-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="57176-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="57176-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57176-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57176-105">Implementa a função de adição interna para a operação RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="57176-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="57176-106">Esta é a operação interna que é conjugada com a operação exterior para construir o adder completo.</span><span class="sxs-lookup"><span data-stu-id="57176-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="57176-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="57176-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="57176-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="57176-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="57176-109">Registo de qubit LittleEndian codificando a primeira entrada e entrada inteiro para RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="57176-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="57176-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="57176-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="57176-111">Registo de qubit LittleEndian codificando a segunda entrada e entrada inteiro para RippleCarryAdderNoCarryTTK.</span><span class="sxs-lookup"><span data-stu-id="57176-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57176-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57176-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="57176-113">Observações</span><span class="sxs-lookup"><span data-stu-id="57176-113">Remarks</span></span>

<span data-ttu-id="57176-114">A operação controlada especificada faz uso da simetria e cancelamento mútuo de operações para melhorar a implementação padrão que adiciona um controlo a cada operação.</span><span class="sxs-lookup"><span data-stu-id="57176-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="57176-115">Referências</span><span class="sxs-lookup"><span data-stu-id="57176-115">References</span></span>

- <span data-ttu-id="57176-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="57176-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530