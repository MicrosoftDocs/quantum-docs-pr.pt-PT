---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operação KnillDistill
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853109"
---
# <a name="knilldistill-operation"></a>Operação KnillDistill

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa o algoritmo de destilação do estado mágico de Knill.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Descrição

Tendo em conta 15 cópias aproximadas de um estado mágico $\ \start{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} \end{align}, $$ rende uma cópia de maior qualidade.

## <a name="input"></a>Entrada

### <a name="roughmagic--qubit"></a>roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de quinze qubits contendo cópias aproximadas de um estado mágico. Após a aplicação deste procedimento de destilação, `roughMagic[0]` conterá uma cópia de maior qualidade, e o resto do registo será reposto para o estado $\ket{00\cdots 0}$ .



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

Se, `true` então, o procedimento tiver sido bem sucedido e a cópia de maior qualidade for aceite. Se `false` o procedimento falhar e o estado do registo for considerado indefinido.

## <a name="remarks"></a>Observações

Seguimos o algoritmo de Knill.
No entanto, a presente implementação está longe de ser a ideal, uma vez que utiliza demasiados qubits.
Os estados mágicos são injetados nesta rotina, e nesse caso há melhores protocolos.

## <a name="references"></a>Referências

- [Rio Knill](https://arxiv.org/abs/quant-ph/0402171)