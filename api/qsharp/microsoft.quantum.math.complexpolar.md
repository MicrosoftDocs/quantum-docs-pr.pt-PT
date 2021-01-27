---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definido pelo utilizador ComplexPolar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847355"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="76553-102">Tipo definido pelo utilizador ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="76553-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="76553-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="76553-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="76553-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76553-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76553-105">Representa um número complexo na forma polar.</span><span class="sxs-lookup"><span data-stu-id="76553-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="76553-106">A representação polar de um número complexo é $c=r e^{i t}$.</span><span class="sxs-lookup"><span data-stu-id="76553-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="76553-107">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="76553-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="76553-108">Magnitude : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="76553-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="76553-109">O valor absoluto $r $0$ de $c$.</span><span class="sxs-lookup"><span data-stu-id="76553-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="76553-110">Argumento : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="76553-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="76553-111">A fase $t \in \mathbb R$ de $c$.</span><span class="sxs-lookup"><span data-stu-id="76553-111">The phase $t \in \mathbb R$ of $c$.</span></span>