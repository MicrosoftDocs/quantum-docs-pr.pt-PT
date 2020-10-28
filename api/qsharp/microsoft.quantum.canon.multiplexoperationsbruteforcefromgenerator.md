---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Operação MultiplexOperationsBruteForceFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2a9bb083b121745bd556aac692d5dc85ffec3791
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715819"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a>Operação MultiplexOperationsBruteForceFromGenerator

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação unitária controlada por multiplicões $U$ que aplica uma $V_j$ unitária quando controlada pelo estado do número n-qubit $\ket{j}$.

$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a>unitárioGenerator :[(Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T = [> Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)

Um tuple onde o primeiro elemento `Int` é o número de unitários $N$, e o segundo elemento é uma `(Int -> ('T => () is Adj + Ctl))` função que leva um inteiro $j$ em $[0,N-1]$ e produz a operação unitária $V_j$.


### <a name="index--littleendian"></a>índice : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n registo de controlo de $-qubit que codifica o número diz $\ket{j}$ em formato pequeno-endian.


### <a name="target--t"></a>alvo : 'T

Registo genérico de qubit que $V_j$ atua.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

`coefficients` serão acolchoados com elementos de identidade se forem especificados menos de $2^n$ . Esta versão é implementada diretamente através de operadores unitários controlados por n.