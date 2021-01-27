---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Operação PrepareIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855879"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="3c38b-102">Operação PrepareIdentity</span><span class="sxs-lookup"><span data-stu-id="3c38b-102">PrepareIdentity operation</span></span>

<span data-ttu-id="3c38b-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3c38b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3c38b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c38b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c38b-105">Dado um registo, prepara-se o registo no estado máximo misto.</span><span class="sxs-lookup"><span data-stu-id="3c38b-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="3c38b-106">O registo é preparado no estado $\boldone / 2^N$ aplicando o canal de despolarizante completo em cada qubit, onde $N$ é o comprimento do registo.</span><span class="sxs-lookup"><span data-stu-id="3c38b-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3c38b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c38b-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="3c38b-108">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c38b-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c38b-109">Um registo cujo estado deve ser despolarizado da forma acima descrita.</span><span class="sxs-lookup"><span data-stu-id="3c38b-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c38b-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c38b-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3c38b-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3c38b-111">See Also</span></span>

- [<span data-ttu-id="3c38b-112">Microsoft.Quantum.preparation.preparesingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="3c38b-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)