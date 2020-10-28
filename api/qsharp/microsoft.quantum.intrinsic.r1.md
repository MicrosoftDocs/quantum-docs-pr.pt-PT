---
uid: Microsoft.Quantum.Intrinsic.R1
title: Operação R1
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720922"
---
# <a name="r1-operation"></a><span data-ttu-id="57bcd-102">Operação R1</span><span class="sxs-lookup"><span data-stu-id="57bcd-102">R1 operation</span></span>

<span data-ttu-id="57bcd-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="57bcd-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="57bcd-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57bcd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57bcd-105">Aplica uma rotação sobre o estado $\ket {1} $ por um determinado ângulo.</span><span class="sxs-lookup"><span data-stu-id="57bcd-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="57bcd-106">\start{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span><span class="sxs-lookup"><span data-stu-id="57bcd-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="57bcd-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="57bcd-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="57bcd-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="57bcd-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="57bcd-109">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="57bcd-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="57bcd-110">Ângulo sobre o qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="57bcd-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="57bcd-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="57bcd-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="57bcd-112">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="57bcd-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57bcd-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57bcd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="57bcd-114">Observações</span><span class="sxs-lookup"><span data-stu-id="57bcd-114">Remarks</span></span>

<span data-ttu-id="57bcd-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="57bcd-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```