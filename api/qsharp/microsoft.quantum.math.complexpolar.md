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
# <a name="complexpolar-user-defined-type"></a>Tipo definido pelo utilizador ComplexPolar

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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