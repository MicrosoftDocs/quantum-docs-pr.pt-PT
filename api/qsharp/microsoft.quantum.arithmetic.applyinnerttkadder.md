---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: AplicaInnerTTKAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721655"
---
# <a name="applyinnerttkadder-operation"></a>AplicaInnerTTKAdder

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Implementa a função de adição interna para a operação RippleCarryAdderTTK. Esta é a operação interna que é conjugada com a operação exterior para construir o adder completo.

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo de qubit LittleEndian codificando a primeira entrada e entrada inteiro para RippleCarryAdderTTK.


### <a name="ys--littleendian"></a>ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo de qubit LittleEndian codificando a segunda entrada e entrada inteiro para RippleCarryAdderTTK.


### <a name="carry--qubit"></a>transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit de transporte, é xored com a parte mais significativa da soma.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A operação controlada especificada faz uso da simetria e cancelamento mútuo de operações para melhorar a implementação padrão que adiciona um controlo a cada operação.

## <a name="references"></a>Referências

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530