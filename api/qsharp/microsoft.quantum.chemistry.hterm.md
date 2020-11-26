---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Tipo definido pelo utilizador HTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204135"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="47d13-102">Tipo definido pelo utilizador HTerm</span><span class="sxs-lookup"><span data-stu-id="47d13-102">HTerm user defined type</span></span>

<span data-ttu-id="47d13-103">Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="47d13-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="47d13-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="47d13-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="47d13-105">Formato de dados passados de C# a Q# para representar um termo do Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="47d13-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="47d13-106">O significado dos dados representados é determinado pelo algoritmo que os recebe.</span><span class="sxs-lookup"><span data-stu-id="47d13-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

