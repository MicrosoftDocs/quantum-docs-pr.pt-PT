---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Estado Modelo de utilizador definido
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722400"
---
# <a name="stategenerator-user-defined-type"></a>Estado Modelo de utilizador definido

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Descreve uma operação que prepara uma dada entrada para um classificador sequencial.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Itens nomeados

### <a name="nqubits--int"></a>NQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits em que a entrada codificada é definida.
### <a name="prepare--littleendian--unit-adj--ctl"></a>Preparar : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Uma operação que prepara a entrada codificada num pequeno registo de `NQubits` qubits.