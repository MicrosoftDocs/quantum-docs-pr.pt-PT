---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operação Multiplicação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719759"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="86caa-102">Operação Multiplicação</span><span class="sxs-lookup"><span data-stu-id="86caa-102">MultiplyI operation</span></span>

<span data-ttu-id="86caa-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="86caa-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="86caa-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86caa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86caa-105">Multiplique o inteiro `xs` por inteiro `ys` e guarde o resultado em , `result` que deve ser zero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="86caa-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="86caa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="86caa-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="86caa-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86caa-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="86caa-108">multiplicand $n$-bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86caa-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="86caa-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86caa-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="86caa-110">multiplicador de $n$-bit (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86caa-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="86caa-111">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="86caa-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="86caa-112">Resultado de $2n$-bit (LittleEndian), deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="86caa-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86caa-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86caa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="86caa-114">Observações</span><span class="sxs-lookup"><span data-stu-id="86caa-114">Remarks</span></span>

<span data-ttu-id="86caa-115">Usa uma abordagem padrão de mudança e adição para implementar a multiplicação.</span><span class="sxs-lookup"><span data-stu-id="86caa-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="86caa-116">A versão controlada foi melhorada copiando $x_i$ para um qubit de ancilla condicionado nos qubits de controlo e, em seguida, controlando a adição no qubit de ancilla.</span><span class="sxs-lookup"><span data-stu-id="86caa-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>