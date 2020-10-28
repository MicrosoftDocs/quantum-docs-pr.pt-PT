---
uid: Microsoft.Quantum.Canon.ApplyBoundCA
title: Operação ApplyBoundCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyBoundCA
qsharp.summary: ''
ms.openlocfilehash: 2b38ec4de40285eff866d9863c1202ee8f8759ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718414"
---
# <a name="applyboundca-operation"></a>Operação ApplyBoundCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)




```qsharp
operation ApplyBoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[], target : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit-adj--ctl"></a>operações : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj + CTL[]




### <a name="target--t"></a>alvo : 'T





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)