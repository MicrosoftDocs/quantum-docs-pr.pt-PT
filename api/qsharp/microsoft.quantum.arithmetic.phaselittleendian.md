---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: FaseLittleEndian tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222427"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="c442e-102">FaseLittleEndian tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="c442e-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="c442e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c442e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c442e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c442e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c442e-105">Pequenos inteiros não assinados na base QFT.</span><span class="sxs-lookup"><span data-stu-id="c442e-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="c442e-106">Por exemplo, se $\ket{x}$ é a codificação pouco-endiana do inteiro $x$ na base computacional, então $\operatorname{QFTLE} \ket{x}$ é a codificação de $x$ na base QFT.</span><span class="sxs-lookup"><span data-stu-id="c442e-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="c442e-107">Observações</span><span class="sxs-lookup"><span data-stu-id="c442e-107">Remarks</span></span>

<span data-ttu-id="c442e-108">`PhaseLittleEndian`Abreviamo-nos como na `PhaseLE` documentação.</span><span class="sxs-lookup"><span data-stu-id="c442e-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c442e-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c442e-109">See Also</span></span>

- [<span data-ttu-id="c442e-110">Microsoft.Quantum.Canon.QFT</span><span class="sxs-lookup"><span data-stu-id="c442e-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="c442e-111">Microsoft.Quantum.Canon.QFTLE</span><span class="sxs-lookup"><span data-stu-id="c442e-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)