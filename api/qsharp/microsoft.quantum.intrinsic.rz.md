---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Operação Rz
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720863"
---
# <a name="rz-operation"></a><span data-ttu-id="3d62c-102">Operação Rz</span><span class="sxs-lookup"><span data-stu-id="3d62c-102">Rz operation</span></span>

<span data-ttu-id="3d62c-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3d62c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3d62c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3d62c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3d62c-105">Aplica uma rotação sobre o eixo $z$por um determinado ângulo.</span><span class="sxs-lookup"><span data-stu-id="3d62c-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="3d62c-106">\start{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \start{bmatrix} e^{-i \theta / 2} & \\ \\ 0 0 & e{i \theta / 2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="3d62c-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="3d62c-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3d62c-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3d62c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3d62c-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="3d62c-109">theta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3d62c-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3d62c-110">Ângulo sobre o qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="3d62c-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="3d62c-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3d62c-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3d62c-112">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="3d62c-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3d62c-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d62c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3d62c-114">Observações</span><span class="sxs-lookup"><span data-stu-id="3d62c-114">Remarks</span></span>

<span data-ttu-id="3d62c-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="3d62c-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```