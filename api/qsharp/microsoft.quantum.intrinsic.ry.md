---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Operação ry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720010"
---
# <a name="ry-operation"></a><span data-ttu-id="5725b-102">Operação ry</span><span class="sxs-lookup"><span data-stu-id="5725b-102">Ry operation</span></span>

<span data-ttu-id="5725b-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5725b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5725b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5725b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5725b-105">Aplica uma rotação sobre o eixo $y$por um determinado ângulo.</span><span class="sxs-lookup"><span data-stu-id="5725b-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="5725b-106">\start{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta} {2} & -\sin \frac{\theta} {2} \\ \\ \sin \frac{\\\\\\\\f\&\\\\\\\ {2} {2}  </span><span class="sxs-lookup"><span data-stu-id="5725b-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="5725b-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5725b-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5725b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="5725b-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="5725b-109">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5725b-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5725b-110">Ângulo sobre o qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="5725b-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="5725b-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5725b-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5725b-112">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="5725b-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5725b-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5725b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5725b-114">Observações</span><span class="sxs-lookup"><span data-stu-id="5725b-114">Remarks</span></span>

<span data-ttu-id="5725b-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="5725b-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```