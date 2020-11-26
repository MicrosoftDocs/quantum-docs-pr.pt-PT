---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definido pelo utilizador ComplexPolar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210986"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="62ba6-102">Tipo definido pelo utilizador ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="62ba6-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="62ba6-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="62ba6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="62ba6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62ba6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62ba6-105">Representa um número complexo na forma polar.</span><span class="sxs-lookup"><span data-stu-id="62ba6-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="62ba6-106">A representação polar de um número complexo é $c=r e^{i t}$.</span><span class="sxs-lookup"><span data-stu-id="62ba6-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="62ba6-107">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="62ba6-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="62ba6-108">Magnitude : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="62ba6-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="62ba6-109">O valor absoluto $r $0$ de $c$.</span><span class="sxs-lookup"><span data-stu-id="62ba6-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="62ba6-110">Argumento : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="62ba6-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="62ba6-111">A fase $t \in \mathbb R$ de $c$.</span><span class="sxs-lookup"><span data-stu-id="62ba6-111">The phase $t \in \mathbb R$ of $c$.</span></span>