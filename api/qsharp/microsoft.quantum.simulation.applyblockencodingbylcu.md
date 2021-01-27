---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Aplicação OperaçãoBlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852816"
---
# <a name="applyblockencodingbylcu-operation"></a>Aplicação OperaçãoBlockEncodingByLCU

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementação de `BlockEncodingByLCU` .

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="statepreparation--t--unit--is-adj--ctl"></a>estatalPreparação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl




### <a name="selector--ts--unit--is-adj--ctl"></a>seletor : ('T'S) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl




### <a name="auxiliary--t"></a>auxiliar : 'T




### <a name="system--s"></a>sistema : 'S





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="s"></a>'S

