---
uid: Microsoft.Quantum.Intrinsic.R
title: R operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 1df4b1197e885e479339e542e8c1ffaeb392543d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818722"
---
# <a name="r-operation"></a><span data-ttu-id="a4e3a-102">R operação</span><span class="sxs-lookup"><span data-stu-id="a4e3a-102">R operation</span></span>

<span data-ttu-id="a4e3a-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a4e3a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a4e3a-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a4e3a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a4e3a-105">Aplica uma rotação sobre o eixo Pauli dado.</span><span class="sxs-lookup"><span data-stu-id="a4e3a-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="a4e3a-106">\start{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} onde $\mu \in \{ I, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="a4e3a-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a4e3a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a4e3a-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a4e3a-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a4e3a-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a4e3a-109">Operador Pauli ($\mu$) a ser exponencial para formar a rotação.</span><span class="sxs-lookup"><span data-stu-id="a4e3a-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="a4e3a-110">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a4e3a-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a4e3a-111">Ângulo sobre o qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="a4e3a-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="a4e3a-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4e3a-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4e3a-113">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="a4e3a-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4e3a-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4e3a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a4e3a-115">Observações</span><span class="sxs-lookup"><span data-stu-id="a4e3a-115">Remarks</span></span>

<span data-ttu-id="a4e3a-116">Quando `pauli = PauliI` convocada, esta operação aplica uma *fase global.*</span><span class="sxs-lookup"><span data-stu-id="a4e3a-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="a4e3a-117">Esta fase pode ser significativa quando usada com o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="a4e3a-117">This phase can be significant when used with the `Controlled` functor.</span></span>