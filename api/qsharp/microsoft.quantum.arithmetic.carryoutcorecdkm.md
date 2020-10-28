---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operação CarryOutCoreCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721306"
---
# <a name="carryoutcorecdkm-operation"></a>Operação CarryOutCoreCDKM

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


A operação principal no RippleCarryAdderCDKM, utilizada com a operação ApplyOuterCDKMAdder, ou seja, conjugada com esta operação para obter o funcionamento interno do RippleCarryAdderCDKM. Esta operação calcula o qubit e aplica uma sequência de portões NOT por parte da entrada `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primeiro registo de qubits.


### <a name="ys--littleendian"></a>ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Segundo registo de qubits.


### <a name="ancilla--qubit"></a>ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit de ancilla usado em RippleCarryAdderCDKM passou para esta operação.


### <a name="carry--qubit"></a>transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Efetuar qubit na operação RippleCarryAdderCDKM.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "Um novo circuito de adição de ondas quânticas", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1