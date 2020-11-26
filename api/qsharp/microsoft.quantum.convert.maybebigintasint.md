---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: Talvez a funçãoBigIntAsInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: d0a598497e8a8f019bbd8da7db1c6cc4d7bde017
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224280"
---
# <a name="maybebigintasint-function"></a>Talvez a funçãoBigIntAsInt

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Converte um dado grande inteiro para um inteiro equivalente, se possível.
A função devolve um par do inteiro resultante e uma bandeira booleana que é verdade, se e somente se a conversão for possível.

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a>Entrada

### <a name="a--bigint"></a>a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--intbool"></a>Saída : ([Int,](xref:microsoft.quantum.lang-ref.int)[Bool)](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Observações

Consulte [c# Grande Construtor de BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para mais detalhes.