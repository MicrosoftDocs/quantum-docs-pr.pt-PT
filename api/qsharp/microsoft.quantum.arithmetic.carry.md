---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operação de transporte
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721307"
---
# <a name="carry-operation"></a>Operação de transporte

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Implementa um portão de transporte reversível. Dado um bit de transporte codificado em qubit `carryIn` e dois bits resumidos `summand1` `summand2` e, calcula o bitwise xor de `carryIn` , e no `summand1` `summand2` qubit e na `summand2` execução é xored para o qubit `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="carryin--qubit"></a>carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de transporte.


### <a name="summand1--qubit"></a>summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Primeiro resumo e qubit.


### <a name="summand2--qubit"></a>summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo resumo e qubit, é substituído pela parte inferior da soma de `summand1` e `summand2` .


### <a name="carryout--qubit"></a>carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de execução, será xored com a parte mais alta da soma.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

