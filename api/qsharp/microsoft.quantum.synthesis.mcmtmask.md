---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definido pelo utilizador MCMTMask
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725497"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="c6215-102">Tipo definido pelo utilizador MCMTMask</span><span class="sxs-lookup"><span data-stu-id="c6215-102">MCMTMask user defined type</span></span>

<span data-ttu-id="c6215-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c6215-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c6215-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6215-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6215-105">Um tipo que representa um portão Toffoli de múltiplos alvos controlados por vários alvos.</span><span class="sxs-lookup"><span data-stu-id="c6215-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="c6215-106">O primeiro inteiro é uma pequena máscara para linhas de controlo.</span><span class="sxs-lookup"><span data-stu-id="c6215-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="c6215-107">Os índices de bits que são definidos correspondem aos índices da linha de controlo.</span><span class="sxs-lookup"><span data-stu-id="c6215-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="c6215-108">O segundo inteiro é uma pequena máscara para as linhas de alvo.</span><span class="sxs-lookup"><span data-stu-id="c6215-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="c6215-109">Os índices de bits que são definidos correspondem aos índices da linha-alvo.</span><span class="sxs-lookup"><span data-stu-id="c6215-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="c6215-110">Os índices de bits de ambos os inteiros devem ser desarticulantes.</span><span class="sxs-lookup"><span data-stu-id="c6215-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="c6215-111">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="c6215-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="c6215-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6215-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="c6215-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6215-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

