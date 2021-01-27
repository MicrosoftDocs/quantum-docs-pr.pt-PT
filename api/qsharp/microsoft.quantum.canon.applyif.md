---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Aplicação OperaçãoIf
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841876"
---
# <a name="applyif-operation"></a>Aplicação OperaçãoIf

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação condicionada a uma parte clássica.

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Descrição

Dada uma operação `op` e um pouco de `bit` valor, aplica-se `op` ao se é `target` `bit` `true` . Se, `false` nada acontecer ao `target` .

## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser aplicada condicionalmente.


### <a name="bit--bool"></a>bit : [Bool](xref:microsoft.quantum.lang-ref.bool)

um booleano que controla se a operação é aplicada ou não.


### <a name="target--t"></a>alvo : 'T

A entrada à qual a operação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar condicionalmente.

## <a name="example"></a>Exemplo

O seguinte prepara um registo de qubits num estado de base computacional representado por uma corda clássica dada como uma matriz de `Bool` valores:

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft.Quantum.Canon.ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft.Quantum.Canon.ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)