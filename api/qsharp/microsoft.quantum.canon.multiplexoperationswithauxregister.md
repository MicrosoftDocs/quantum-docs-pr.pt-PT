---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Operação MultiplexOperationsWithAuxRegister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: f6a90657324f8528aaa2e9e511a7f8cbcd2f540f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715791"
---
# <a name="multiplexoperationswithauxregister-operation"></a>Operação MultiplexOperationsWithAuxRegister

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Passo de implementação de MultiplexOperations.

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="unitaries--t--unit-adj--ctl"></a>unitários : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + CTL[]




### <a name="auxillaryregister--qubit"></a>auxillaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>índice : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>alvo : 'T





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.MultiplexOperations](xref:Microsoft.Quantum.Canon.MultiplexOperations)