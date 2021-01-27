---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: Aplicar Operação Operação Operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842008"
---
# <a name="applyandchain-operation"></a>Aplicar Operação Operação Operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula uma cadeia de portões E

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a>Descrição

Os qubits auxiliares para calcular os resultados temporários devem ser explicitamente especificados.
O comprimento desse registo é `Length(ctrlRegister) - 2` , se houver pelo menos dois controlos, caso contrário o comprimento é 0.

## <a name="input"></a>Entrada

### <a name="auxregister--qubit"></a>auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="ctrlregister--qubit"></a>ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

