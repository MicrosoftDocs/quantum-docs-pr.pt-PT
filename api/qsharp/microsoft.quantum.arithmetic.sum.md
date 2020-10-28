---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operação sum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719506"
---
# <a name="sum-operation"></a>Operação sum

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Implementa um portão de soma reversível. Dado um bit de transporte codificado em qubit `carryIn` e dois bits resumidos `summand1` `summand2` e, calcula o bitwise xor de `carryIn` , e no `summand1` `summand2` qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="carryin--qubit"></a>carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de transporte.


### <a name="summand1--qubit"></a>summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Primeiro resumo e qubit.


### <a name="summand2--qubit"></a>summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo resumo e qubit, é substituído pela parte inferior da soma de `summand1` e `summand2` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Em contraste com a `Carry` operação, isto não calcula a parte de execução.