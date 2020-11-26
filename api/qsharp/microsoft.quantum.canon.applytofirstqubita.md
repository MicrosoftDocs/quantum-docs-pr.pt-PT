---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Aplicar operaçãoToFirstQubitA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208844"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="3224b-102">Aplicar operaçãoToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="3224b-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="3224b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3224b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3224b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3224b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3224b-105">Aplica uma operação ao primeiro qubit no registo.</span><span class="sxs-lookup"><span data-stu-id="3224b-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="3224b-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="3224b-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="3224b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="3224b-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="3224b-108">op [Qubit](xref:microsoft.quantum.lang-ref.qubit) : => [Qubit Unit](xref:microsoft.quantum.lang-ref.unit) é Adj</span><span class="sxs-lookup"><span data-stu-id="3224b-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3224b-109">Uma operação a ser aplicada ao primeiro qubit</span><span class="sxs-lookup"><span data-stu-id="3224b-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3224b-110">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3224b-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3224b-111">Qubit array para o primeiro qubit de qual a operação é aplicada</span><span class="sxs-lookup"><span data-stu-id="3224b-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3224b-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3224b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3224b-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3224b-113">See Also</span></span>

- [<span data-ttu-id="3224b-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="3224b-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)