---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operação GreaterTh
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721138"
---
# <a name="greaterthan-operation"></a>Operação GreaterTh

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Aplica uma comparação maior do que a comparação entre dois inteiros codificados em registos qubit, lançando um qubit alvo com base no resultado da comparação.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a>Descrição

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