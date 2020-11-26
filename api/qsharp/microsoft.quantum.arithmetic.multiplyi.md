---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operação Multiplicação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222512"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="2ccd3-102">Operação Multiplicação</span><span class="sxs-lookup"><span data-stu-id="2ccd3-102">MultiplyI operation</span></span>

<span data-ttu-id="2ccd3-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2ccd3-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="2ccd3-105">Multiplique o inteiro `xs` por inteiro `ys` e guarde o resultado em , `result` que deve ser zero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="2ccd3-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2ccd3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ccd3-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="2ccd3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2ccd3-108">multiplicand $n$-bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="2ccd3-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2ccd3-110">multiplicador de $n$-bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="2ccd3-111">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2ccd3-112">Resultado de $2n$-bit (LittleEndian), deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="2ccd3-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ccd3-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ccd3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2ccd3-114">Observações</span><span class="sxs-lookup"><span data-stu-id="2ccd3-114">Remarks</span></span>

<span data-ttu-id="2ccd3-115">Usa uma abordagem padrão de mudança e adição para implementar a multiplicação.</span><span class="sxs-lookup"><span data-stu-id="2ccd3-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="2ccd3-116">A versão controlada foi melhorada copiando $x_i$ para um qubit de ancilla condicionado nos qubits de controlo e, em seguida, controlando a adição no qubit de ancilla.</span><span class="sxs-lookup"><span data-stu-id="2ccd3-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>