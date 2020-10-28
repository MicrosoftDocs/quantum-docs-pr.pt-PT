---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Operação RippleCarryAdderCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: 6dcb5193c5d1d059682a79e63e6562aabff7539d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719614"
---
# <a name="ripplecarryaddercdkm-operation"></a>Operação RippleCarryAdderCDKM

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Reversível, adição de dois inteiros.

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="description"></a>Descrição

Tendo em conta dois inteiros $n de $-bit codificados nos registos de LittleEndian `xs` e , e um transporte `ys` qubit, a operação calcula a soma dos dois inteiros onde os $n$ menos significativos do resultado são mantidos `ys` e a broca de execução é recortada ao qubit `carry` .

## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo de qubit littleEndian codificando o primeiro resumo inteiro.


### <a name="ys--littleendian"></a>ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O registo de qubits LittleEndian codificando o segundo resumo inteiro, é modificado para manter os pedaços menos significativos da soma.


### <a name="carry--qubit"></a>transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit de transporte, é xored com a parte mais significativa da soma.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Esta operação tem a mesma funcionalidade que o RippleCarryAdderD, mas utiliza apenas um qubit auxiliar em vez de $n$.

## <a name="references"></a>Referências

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "Um novo circuito de adição de ondas quânticas", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1