---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operação de reset
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818634"
---
# <a name="reset-operation"></a><span data-ttu-id="fac1c-102">Operação de reset</span><span class="sxs-lookup"><span data-stu-id="fac1c-102">Reset operation</span></span>

<span data-ttu-id="fac1c-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fac1c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fac1c-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fac1c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fac1c-105">Dado um único qubit, mede-o e assegura-o de que está no |0⟩ estado de modo a que possa ser libertado com segurança.</span><span class="sxs-lookup"><span data-stu-id="fac1c-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fac1c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fac1c-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="fac1c-107">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fac1c-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fac1c-108">O qubit cujo estado deve ser reposto para $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fac1c-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fac1c-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fac1c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

