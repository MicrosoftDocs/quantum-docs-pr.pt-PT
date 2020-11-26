---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operação GreaterTh
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 644d68affbdb508938f76de5025a1a463e7284e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223090"
---
# <a name="greaterthan-operation"></a>Operação GreaterTh

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma comparação maior do que a comparação entre dois inteiros codificados em registos qubit, lançando um qubit alvo com base no resultado da comparação.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Realiza uma comparação estritamente maior do que a comparação de dois inteiros $x$ e $y$, codificados em qubit registers xs e ys. Se $x > y$, então o qubit do resultado será invertido, caso contrário o qubit de resultado manterá o seu estado.

## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo de qubit littleEndian codificando o primeiro inteiro $x$.


### <a name="ys--littleendian"></a>ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo de qubit littleEndian codificando o segundo número inteiro $y$.


### <a name="result--qubit"></a>resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um único qubit que será virado se $x > y$.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Usa o truque que $x - y = (x'+y)'$,'$, onde ' denota o complemento do outro.

## <a name="references"></a>Referências

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "Um novo circuito de adição de ondas quânticas", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits com multiplicação modular baseada em Toffoli", 2016 https://arxiv.org/abs/1611.07995