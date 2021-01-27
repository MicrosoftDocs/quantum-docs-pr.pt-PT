---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Operação Rz
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 4282fcc216173234ec742991b8f0fa1be203da0d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849277"
---
# <a name="rz-operation"></a><span data-ttu-id="e887e-102">Operação Rz</span><span class="sxs-lookup"><span data-stu-id="e887e-102">Rz operation</span></span>

<span data-ttu-id="e887e-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e887e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e887e-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e887e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e887e-105">Aplica uma rotação sobre o eixo $z$por um determinado ângulo.</span><span class="sxs-lookup"><span data-stu-id="e887e-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="e887e-106">\start{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \start{bmatrix} e^{-i \theta / 2} & \\ \\ 0 0 & e{i \theta / 2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="e887e-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="e887e-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e887e-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e887e-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e887e-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="e887e-109">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e887e-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e887e-110">Ângulo sobre o qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="e887e-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e887e-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e887e-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e887e-112">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="e887e-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e887e-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e887e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e887e-114">Observações</span><span class="sxs-lookup"><span data-stu-id="e887e-114">Remarks</span></span>

<span data-ttu-id="e887e-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="e887e-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```