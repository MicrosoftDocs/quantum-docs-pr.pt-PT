---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operação KnillDistill
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712277"
---
# <a name="knilldistill-operation"></a>Operação KnillDistill

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


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