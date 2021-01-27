---
uid: Microsoft.Quantum.Intrinsic.R1
title: Operação R1
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 07cce580b50fef5664fdac32bb4fae0ba22d25e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849356"
---
# <a name="r1-operation"></a><span data-ttu-id="a0bb3-102">Operação R1</span><span class="sxs-lookup"><span data-stu-id="a0bb3-102">R1 operation</span></span>

<span data-ttu-id="a0bb3-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a0bb3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a0bb3-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a0bb3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a0bb3-105">Aplica uma rotação sobre o estado $\ket {1} $ por um determinado ângulo.</span><span class="sxs-lookup"><span data-stu-id="a0bb3-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="a0bb3-106">\start{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span><span class="sxs-lookup"><span data-stu-id="a0bb3-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="a0bb3-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a0bb3-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a0bb3-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a0bb3-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="a0bb3-109">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a0bb3-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a0bb3-110">Ângulo sobre o qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="a0bb3-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="a0bb3-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a0bb3-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a0bb3-112">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="a0bb3-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0bb3-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0bb3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a0bb3-114">Observações</span><span class="sxs-lookup"><span data-stu-id="a0bb3-114">Remarks</span></span>

<span data-ttu-id="a0bb3-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="a0bb3-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```