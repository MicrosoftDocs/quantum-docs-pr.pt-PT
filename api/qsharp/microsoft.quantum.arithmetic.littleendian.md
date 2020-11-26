---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: Tipo definido pelo utilizador LittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222784"
---
# <a name="littleendian-user-defined-type"></a>Tipo definido pelo utilizador LittleEndian

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Registe-se que codifica um número inteiro não assinado em ordem de pequeno-endian. O qubit com índice `0` codifica a parte mais baixa de um número inteiro não assinado.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Observações

`LittleEndian`Abreviamo-nos como na `LE` documentação.