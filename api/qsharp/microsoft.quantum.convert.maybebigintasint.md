---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: Talvez a funçãoBigIntAsInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713436"
---
# <a name="maybebigintasint-function"></a>Talvez a funçãoBigIntAsInt

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [](https://nuget.org/packages/)


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