---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Tipo definido pelo utilizador BlockEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 75fdbf13cf07d906982d4a611d1d25b3e29db2cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225436"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="a279e-102">Tipo definido pelo utilizador BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="a279e-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="a279e-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a279e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a279e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a279e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a279e-105">Representa um operador unitário onde um operador de interesse arbitrário é codificado no bloco superior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="a279e-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="a279e-106">Ou seja, `BlockEncoding` é um $U$ unitário onde um operador arbitrário $H dólares de juros que atua no registo do sistema `s` é codificado no bloco superior esquerdo correspondente ao estado auxiliar $\ket {0} _a$.</span><span class="sxs-lookup"><span data-stu-id="a279e-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="a279e-107">Isso é</span><span class="sxs-lookup"><span data-stu-id="a279e-107">That is,</span></span>

<span data-ttu-id="a279e-108">$$ \start{align} (\bra {0} _a\otimes I_s)U(\ket {0} _a\otimes I_s) = H \end{align} $$.</span><span class="sxs-lookup"><span data-stu-id="a279e-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

