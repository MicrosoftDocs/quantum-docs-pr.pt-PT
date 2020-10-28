---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Operação RippleCarryAdderTTK
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719566"
---
# <a name="ripplecarryadderttk-operation"></a>Operação RippleCarryAdderTTK

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Reversível, adição de dois inteiros.
Tendo em conta dois inteiros $n de $-bit codificados nos registos de LittleEndian `xs` e , e um transporte `ys` qubit, a operação calcula a soma dos dois inteiros onde os $n$ menos significativos do resultado são mantidos `ys` e a broca de execução é recortada ao qubit `carry` .

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo de qubit littleEndian codificando o primeiro resumo inteiro.


### <a name="ys--littleendian"></a>ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O registo de qubits LittleEndian codificando o segundo resumo inteiro, é modificado para manter o $n$ menos significativo da soma.


### <a name="carry--qubit"></a>transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit de transporte, é xored com a parte mais significativa da soma.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Esta operação tem a mesma funcionalidade que o RippleCarryAdderD e, RippleCarryAdderCDKM, mas não utiliza qubits de oscilação.

## <a name="references"></a>Referências

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530