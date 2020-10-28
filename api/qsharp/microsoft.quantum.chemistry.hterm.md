---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Tipo definido pelo utilizador HTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714867"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="0fac7-102">Tipo definido pelo utilizador HTerm</span><span class="sxs-lookup"><span data-stu-id="0fac7-102">HTerm user defined type</span></span>

<span data-ttu-id="0fac7-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0fac7-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="0fac7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0fac7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0fac7-105">Formato de dados passados de C# a Q# para representar um termo do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="0fac7-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="0fac7-106">O significado dos dados representados é determinado pelo algoritmo que os recebe.</span><span class="sxs-lookup"><span data-stu-id="0fac7-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

