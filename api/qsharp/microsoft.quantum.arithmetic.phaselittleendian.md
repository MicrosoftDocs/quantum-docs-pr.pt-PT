---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: FaseLittleEndian tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842991"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="0bdf9-102">FaseLittleEndian tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="0bdf9-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="0bdf9-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0bdf9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0bdf9-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bdf9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bdf9-105">Pequenos inteiros não assinados na base QFT.</span><span class="sxs-lookup"><span data-stu-id="0bdf9-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="0bdf9-106">Por exemplo, se $\ket{x}$ é a codificação pouco-endiana do inteiro $x$ na base computacional, então $\operatorname{QFTLE} \ket{x}$ é a codificação de $x$ na base QFT.</span><span class="sxs-lookup"><span data-stu-id="0bdf9-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="0bdf9-107">Observações</span><span class="sxs-lookup"><span data-stu-id="0bdf9-107">Remarks</span></span>

<span data-ttu-id="0bdf9-108">`PhaseLittleEndian`Abreviamo-nos como na `PhaseLE` documentação.</span><span class="sxs-lookup"><span data-stu-id="0bdf9-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bdf9-109">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0bdf9-109">See Also</span></span>

- [<span data-ttu-id="0bdf9-110">Microsoft.Quantum.Canon.QFT</span><span class="sxs-lookup"><span data-stu-id="0bdf9-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="0bdf9-111">Microsoft.Quantum.Canon.QFTLE</span><span class="sxs-lookup"><span data-stu-id="0bdf9-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)