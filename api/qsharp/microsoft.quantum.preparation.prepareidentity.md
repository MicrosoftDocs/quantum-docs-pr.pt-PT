---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operação PrepareIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724892"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="7b836-102">Operação PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="7b836-102">PrepareIdentity operation</span></span>

<span data-ttu-id="7b836-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7b836-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7b836-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b836-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b836-105">Dado um registo, prepara-se o registo no estado máximo misto.</span><span class="sxs-lookup"><span data-stu-id="7b836-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="7b836-106">O registo é preparado no estado $\boldone / 2^N$ aplicando o canal de despolarizante completo em cada qubit, onde $N$ é o comprimento do registo.</span><span class="sxs-lookup"><span data-stu-id="7b836-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7b836-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7b836-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="7b836-108">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7b836-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7b836-109">Um registo cujo estado deve ser despolarizado da forma acima descrita.</span><span class="sxs-lookup"><span data-stu-id="7b836-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b836-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b836-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7b836-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7b836-111">See Also</span></span>

- [<span data-ttu-id="7b836-112">Microsoft.Quantum.preparation.preparesingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="7b836-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)