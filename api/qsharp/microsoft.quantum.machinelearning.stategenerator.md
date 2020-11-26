---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Estado Modelo de utilizador definido
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211564"
---
# <a name="stategenerator-user-defined-type"></a>Estado Modelo de utilizador definido

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Descreve uma operação que prepara uma dada entrada para um classificador sequencial.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Itens nomeados

### <a name="nqubits--int"></a>NQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que a entrada codificada é definida.
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>Preparar : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl

Uma operação que prepara a entrada codificada num pequeno registo de `NQubits` qubits.