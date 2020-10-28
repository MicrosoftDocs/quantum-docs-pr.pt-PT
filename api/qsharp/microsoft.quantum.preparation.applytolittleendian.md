---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Aplicar OperaçãoLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724108"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="95b1b-102">Aplicar OperaçãoLittleEndian</span><span class="sxs-lookup"><span data-stu-id="95b1b-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="95b1b-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="95b1b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="95b1b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95b1b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95b1b-105">Aplica uma operação aos qubits subjacentes que compõem um pequeno registo endiano.</span><span class="sxs-lookup"><span data-stu-id="95b1b-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="95b1b-106">Esta operação é marcada como interna, uma vez que um registo de pequenas extremidades pretende ser "opaco", de tal forma que se trata apenas de um detalhe de implementação.</span><span class="sxs-lookup"><span data-stu-id="95b1b-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="95b1b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="95b1b-107">Input</span></span>

### <a name="bareop--qubit--unit-adj--ctl"></a><span data-ttu-id="95b1b-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = unidade> [Adj](xref:microsoft.quantum.lang-ref.unit) + Ctl</span><span class="sxs-lookup"><span data-stu-id="95b1b-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="95b1b-109">registo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="95b1b-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="95b1b-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95b1b-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

