---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordina a função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724080"
---
# <a name="blochspherecoordinates-function"></a><span data-ttu-id="fac88-102">BlochSphereCoordina a função</span><span class="sxs-lookup"><span data-stu-id="fac88-102">BlochSphereCoordinates function</span></span>

<span data-ttu-id="fac88-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="fac88-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="fac88-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fac88-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fac88-105">Calcula as coordenadas da esfera Bloch para um estado de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="fac88-105">Computes the Bloch sphere coordinates for a single-qubit state.</span></span>

<span data-ttu-id="fac88-106">Dado dois números complexos $a 0, a1$ que representam o estado qubit, calcula as coordenadas na esfera bloch de tal forma que $a 0 \ket {0} + a1 \ket {1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket {0} +e^{i \phi /2}\infry(\theta/2}).ket {1}</span><span class="sxs-lookup"><span data-stu-id="fac88-106">Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.</span></span>

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a><span data-ttu-id="fac88-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="fac88-107">Input</span></span>

### <a name="a0--complexpolar"></a><span data-ttu-id="fac88-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="fac88-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="fac88-109">Coeficiente complexo de estado $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="fac88-109">Complex coefficient of state $\ket{0}$.</span></span>


### <a name="a1--complexpolar"></a><span data-ttu-id="fac88-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="fac88-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="fac88-111">Coeficiente complexo de estado $\ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="fac88-111">Complex coefficient of state $\ket{1}$.</span></span>



## <a name="output--complexpolardoubledouble"></a><span data-ttu-id="fac88-112">Saída :[(ComplexPolar,](xref:Microsoft.Quantum.Math.ComplexPolar)[Double,](xref:microsoft.quantum.lang-ref.double)[Double)](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fac88-112">Output : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="fac88-113">Uma tuple `(ComplexPolar(r, t), phi, theta)` contendo.</span><span class="sxs-lookup"><span data-stu-id="fac88-113">A tuple containing `(ComplexPolar(r, t), phi, theta)`.</span></span>