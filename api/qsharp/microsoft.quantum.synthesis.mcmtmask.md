---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definido pelo utilizador MCMTMask
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203028"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="57d76-102">Tipo definido pelo utilizador MCMTMask</span><span class="sxs-lookup"><span data-stu-id="57d76-102">MCMTMask user defined type</span></span>

<span data-ttu-id="57d76-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="57d76-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="57d76-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57d76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57d76-105">Um tipo que representa um portão Toffoli de múltiplos alvos controlados por vários alvos.</span><span class="sxs-lookup"><span data-stu-id="57d76-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="57d76-106">O primeiro inteiro é uma pequena máscara para linhas de controlo.</span><span class="sxs-lookup"><span data-stu-id="57d76-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="57d76-107">Os índices de bits que são definidos correspondem aos índices da linha de controlo.</span><span class="sxs-lookup"><span data-stu-id="57d76-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="57d76-108">O segundo inteiro é uma pequena máscara para as linhas de alvo.</span><span class="sxs-lookup"><span data-stu-id="57d76-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="57d76-109">Os índices de bits que são definidos correspondem aos índices da linha-alvo.</span><span class="sxs-lookup"><span data-stu-id="57d76-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="57d76-110">Os índices de bits de ambos os inteiros devem ser desarticulantes.</span><span class="sxs-lookup"><span data-stu-id="57d76-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="57d76-111">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="57d76-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="57d76-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57d76-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="57d76-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57d76-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

