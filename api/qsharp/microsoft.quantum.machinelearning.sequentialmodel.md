---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definido pelo utilizador sequencialModel
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854901"
---
# <a name="sequentialmodel-user-defined-type"></a>Tipo definido pelo utilizador sequencialModel

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Descreve um modelo de classificador quântico composto por uma sequência de rotações parametrizadas e controladas, uma atribuição de ângulos de rotação, e um enviesamento entre as duas classes reconhecidas pelo modelo.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Itens nomeados

### <a name="structure--controlledrotation"></a>Estrutura : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

A sequência de rotações controladas usadas para classificar as entradas.
### <a name="parameters--double"></a>Parâmetros : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma atribuição de ângulos de rotação à estrutura de classificação dada.
### <a name="bias--double"></a>Preconceito : [Duplo](xref:microsoft.quantum.lang-ref.double)

O enviesamento entre as duas classes reconhecidas por este classificador.

## <a name="references"></a>Referências

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)