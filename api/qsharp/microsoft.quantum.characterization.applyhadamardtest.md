---
uid: Microsoft.Quantum.Characterization.ApplyHadamardTest
title: Aplicar operaçãoHadamardTest
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ApplyHadamardTest
qsharp.summary: ''
ms.openlocfilehash: 6fcbc81faa7c177874d102041daacd4e62a97737
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715130"
---
# <a name="applyhadamardtest-operation"></a>Aplicar operaçãoHadamardTest

Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)

Pacote: [](https://nuget.org/packages/)




```qsharp
operation ApplyHadamardTest (phaseShift : Bool, commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), control : Qubit, target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="phaseshift--bool"></a>phaseShift : [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="commonpreparation--qubit--unit-adj"></a>comunsPreparação : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj




### <a name="preparation1--qubit--unit-adj--ctl"></a>preparação1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = unidade> [Adj](xref:microsoft.quantum.lang-ref.unit) + Ctl




### <a name="preparation2--qubit--unit-adj--ctl"></a>preparação2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl




### <a name="control--qubit"></a>controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

