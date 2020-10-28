---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Aplicação OperaçãoBlockEncodingByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722123"
---
# <a name="applyblockencodingbylcu-operation"></a>Aplicação OperaçãoBlockEncodingByLCU

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Implementação de `BlockEncodingByLCU` .

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>Entrada

### <a name="statepreparation--t--unit-adj--ctl"></a>estatalPreparação : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj + Ctl




### <a name="selector--ts--unit-adj--ctl"></a>seletor : ('T'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl




### <a name="auxiliary--t"></a>auxiliar : 'T




### <a name="system--s"></a>sistema : 'S





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="s"></a>'S

