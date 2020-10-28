---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TempoDependentBlockEncoding tipo definido do utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: 1cb3a3cf1e16b194eebd1574da6f9934fc34e5f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725760"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="8eb5d-102">TempoDependentBlockEncoding tipo definido do utilizador</span><span class="sxs-lookup"><span data-stu-id="8eb5d-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="8eb5d-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8eb5d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8eb5d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8eb5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8eb5d-105">Representa um `BlockEncoding` que é controlado por um registo de relógio.</span><span class="sxs-lookup"><span data-stu-id="8eb5d-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="8eb5d-106">Ou seja, `TimeDependentBlockEncoding` um $U$ unitário controlado por um estado $\ket{k}_d$ no registo do relógio `d` de modo a que um operador arbitrário $H_k$ de juros que atua no registo do sistema `s` esteja codificado no bloco superior esquerdo correspondente ao estado auxiliar $\ket {0} _a$.</span><span class="sxs-lookup"><span data-stu-id="8eb5d-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="8eb5d-107">Isso é</span><span class="sxs-lookup"><span data-stu-id="8eb5d-107">That is,</span></span>

<span data-ttu-id="8eb5d-108">$$ \begin{align} (\bra {0} \_ a\otimes I_{ds})U(\ket {0} \_ a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k} \_ d\otimes H_k.</span><span class="sxs-lookup"><span data-stu-id="8eb5d-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="8eb5d-109">\end{align} $$.</span><span class="sxs-lookup"><span data-stu-id="8eb5d-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

