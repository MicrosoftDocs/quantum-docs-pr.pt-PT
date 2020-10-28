---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operação LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715928"
---
# <a name="logicalandmeasandfix-operation"></a>Operação LogicalANDMeasAndFix

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Calcula a lógica e de múltiplos qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="ctrlregister--qubit"></a>ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits entrada para o portão E de entrada múltipla.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit em que saída de E é escrita para. Isto é assumido para sempre começar no estado $\ket {0} $.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Quando `ctrlRegister` tem exatamente $2$ qubits, isto é equivalente à `CCNOT` operação, mas fase com uma fase $e^{i\Pi/2}$ em $\ket {001} $ e $-e^{i\Pi/2}$ em $\ket {101} $ e $\ket {011} $.
O Adjacente é também uma abordagem de medida e fixação que é o inverso da operação original apenas em casos especiais (ver referências), mas utiliza menos portas T.

## <a name="references"></a>Referências

- [*Craig Gidney* , 1709.06648](https://arxiv.org/abs/1709.06648)