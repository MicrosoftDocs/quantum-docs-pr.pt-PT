---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Aplicar operação ToHead
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841326"
---
# <a name="applytohead-operation"></a>Aplicar operação ToHead

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação ao primeiro elemento de uma matriz.

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Descrição

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais o primeiro será aplicado `op` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="example"></a>Exemplo

Os seguintes cortes Q# são equivalentes:

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToHeada](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft.Quantum.Canon.ApplyToHeadc](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft.Quantum.Canon.ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)