---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Aplicação OperaçãoToRestCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: e64eeaae2151a28c289e3e71e47f897d6c378b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841250"
---
# <a name="applytorestca-operation"></a>Aplicação OperaçãoToRestCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação a todos menos ao primeiro elemento de uma matriz.

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj--ctl"></a>op : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyTorest](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft.Quantum.Canon.ApplyToresta](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft.Quantum.Canon.ApplyTorestC](xref:Microsoft.Quantum.Canon.ApplyToRestC)