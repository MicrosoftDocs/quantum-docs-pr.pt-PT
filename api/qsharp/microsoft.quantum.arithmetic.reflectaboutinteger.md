---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Refletir Sobre a operação Deinteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719711"
---
# <a name="reflectaboutinteger-operation"></a>Refletir Sobre a operação Deinteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Reflete um registo quântico sobre um dado número inteiro clássico.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrição

Dado um registo quântico inicialmente no estado $\sum_i \alpha_i \ket{i}$, onde cada $\ket{i}$ é um estado de base que representa um número inteiro $i$, reflete o estado do registo sobre o estado de base para um dado inteiro $\ket{j}$, $$ \sum_i (-1)^{\ \delta_{ij} } \alpha_i \ket{i} $$

## <a name="input"></a>Entrada

### <a name="index--int"></a>índice : [Int](xref:microsoft.quantum.lang-ref.int)

O inteiro clássico indexando o estado de base sobre o qual refletir.


### <a name="reg--littleendian"></a>reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Esta operação é implementada no local, sem atribuição explícita de qubits auxiliares adicionais.