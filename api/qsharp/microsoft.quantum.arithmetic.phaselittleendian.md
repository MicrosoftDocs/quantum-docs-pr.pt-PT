---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: FaseLittleEndian tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719734"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="a3703-102">FaseLittleEndian tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="a3703-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="a3703-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3703-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3703-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3703-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3703-105">Pequenos inteiros não assinados na base QFT.</span><span class="sxs-lookup"><span data-stu-id="a3703-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="a3703-106">Por exemplo, se $\ket{x}$ é a codificação pouco-endiana do inteiro $x$ na base computacional, então $\operatorname{QFTLE} \ket{x}$ é a codificação de $x$ na base QFT.</span><span class="sxs-lookup"><span data-stu-id="a3703-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="a3703-107">Observações</span><span class="sxs-lookup"><span data-stu-id="a3703-107">Remarks</span></span>

<span data-ttu-id="a3703-108">`PhaseLittleEndian`Abreviamo-nos como na `PhaseLE` documentação.</span><span class="sxs-lookup"><span data-stu-id="a3703-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3703-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a3703-109">See Also</span></span>

- [<span data-ttu-id="a3703-110">Microsoft.Quantum.Canon.QFT</span><span class="sxs-lookup"><span data-stu-id="a3703-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="a3703-111">Microsoft.Quantum.Canon.QFTLE</span><span class="sxs-lookup"><span data-stu-id="a3703-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)