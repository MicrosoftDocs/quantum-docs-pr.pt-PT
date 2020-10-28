---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: Função BoolArrayAsBigInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713618"
---
# <a name="boolarrayasbigint-function"></a>Função BoolArrayAsBigInt

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [](https://nuget.org/packages/)


Converte uma certa variedade de Booleans para um número inteiro equivalente.
O elemento 0 da matriz é a parte menos significativa do grande número inteiro.

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>Entrada

### <a name="a--bool"></a>a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Observações

Consulte [c# Grande Construtor de BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) para mais detalhes.