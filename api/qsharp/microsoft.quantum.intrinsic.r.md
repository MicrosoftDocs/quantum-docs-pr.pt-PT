---
uid: Microsoft.Quantum.Intrinsic.R
title: R operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199034"
---
# <a name="r-operation"></a><span data-ttu-id="93656-102">R operação</span><span class="sxs-lookup"><span data-stu-id="93656-102">R operation</span></span>

<span data-ttu-id="93656-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="93656-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="93656-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="93656-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="93656-105">Aplica uma rotação sobre o eixo Pauli dado.</span><span class="sxs-lookup"><span data-stu-id="93656-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="93656-106">\start{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} onde $\mu \in \{ I, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="93656-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="93656-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="93656-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="93656-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="93656-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="93656-109">Operador Pauli ($\mu$) a ser exponencial para formar a rotação.</span><span class="sxs-lookup"><span data-stu-id="93656-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="93656-110">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="93656-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="93656-111">Ângulo sobre o qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="93656-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="93656-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="93656-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="93656-113">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="93656-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93656-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93656-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="93656-115">Observações</span><span class="sxs-lookup"><span data-stu-id="93656-115">Remarks</span></span>

<span data-ttu-id="93656-116">Quando `pauli = PauliI` convocada, esta operação aplica uma *fase global.*</span><span class="sxs-lookup"><span data-stu-id="93656-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="93656-117">Esta fase pode ser significativa quando usada com o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="93656-117">This phase can be significant when used with the `Controlled` functor.</span></span>