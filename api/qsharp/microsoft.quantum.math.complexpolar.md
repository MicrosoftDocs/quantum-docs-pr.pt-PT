---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definido pelo utilizador ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709645"
---
# <a name="complexpolar-user-defined-type"></a>Tipo definido pelo utilizador ComplexPolar

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [](https://nuget.org/packages/)


Representa um número complexo na forma polar.

A representação polar de um número complexo é $c=r e^{i t}$.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Itens nomeados

### <a name="magnitude--double"></a>Magnitude : [Duplo](xref:microsoft.quantum.lang-ref.double)

O valor absoluto $r $0$ de $c$.
### <a name="argument--double"></a>Argumento : [Duplo](xref:microsoft.quantum.lang-ref.double)

A fase $t \in \mathbb R$ de $c$.