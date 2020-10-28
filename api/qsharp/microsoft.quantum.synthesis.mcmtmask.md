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
# <a name="mcmtmask-user-defined-type"></a>Tipo definido pelo utilizador MCMTMask

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)


Um tipo que representa um portão Toffoli de múltiplos alvos controlados por vários alvos.

O primeiro inteiro é uma pequena máscara para linhas de controlo.  Os índices de bits que são definidos correspondem aos índices da linha de controlo.

O segundo inteiro é uma pequena máscara para as linhas de alvo.  Os índices de bits que são definidos correspondem aos índices da linha-alvo.

Os índices de bits de ambos os inteiros devem ser desarticulantes.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="controlmask--int"></a>ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)

