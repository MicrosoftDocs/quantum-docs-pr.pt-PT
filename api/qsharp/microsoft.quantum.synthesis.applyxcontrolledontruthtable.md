---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: AplicaxControlledOnTruthTable
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 6e956038f7cd15db7348ff830da8bc9eae53aa61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855552"
---
# <a name="applyxcontrolledontruthtable-operation"></a>AplicaxControlledOnTruthTable

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica a @"microsoft.quantum.intrinsic.x" operação em `target` , se a função Boolean `func` avaliar a verdade para a atribuição clássica em `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

A operação implementa a operação unitária \start{align} U\ket{x}ket{y} = \ket{x}ket{y \oplus f(x)} \end{align} onde $x$ e $y$ representam `controlRegister` `target` e, respectivamente.

A função Booleana $f$ é representada como uma mesa de verdade em termos de um grande número inteiro.
Por exemplo, a função maioritária em três entradas é representada pelo bitstring `11101000` , onde a parte mais significativa corresponde à atribuição de entrada , e a parte menos significativa `1` corresponde à atribuição de entrada `(1, 1, 1)` `0` `(0, 0, 0)` .
Pode ser representado pelo grande número inteiro `0xE8L` na notação hexadecimal ou como `232L` na notação decimal.  O `L` sufixo indica que a constante é do tipo `BigInt` .
Mais detalhes sobre esta representação também podem ser encontrados nas tabelas da [verdade kata.](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)

A implementação faz uso e @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" portões.

## <a name="input"></a>Entrada

### <a name="func--bigint"></a>func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Mesa da verdade booleana representada como grande inteiro


### <a name="controlregister--qubit"></a>controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de qubits de controlo


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit alvo



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- [*N. Schuch*, *J. Siewert*, PRL 91, nº 027902, 2003, arXiv:quant-ph/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken*, *Martin Roetteler,* arXiv:2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)