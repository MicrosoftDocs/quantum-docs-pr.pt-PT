---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: AplicarOperação Funcionar
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 65e861914b57cf8a32f2321f881248830b72c54e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841912"
---
# <a name="applycurriedopc-operation"></a>AplicarOperação Funcionar

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit--is-ctl"></a>curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL




### <a name="first--t"></a>primeiro : 'T




### <a name="second--u"></a>segundo : 'U





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="u"></a>'U

