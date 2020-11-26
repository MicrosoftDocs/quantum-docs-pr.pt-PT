---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Requer tipo definido pelo utilizadorCapability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231012"
---
# <a name="requirescapability-user-defined-type"></a>Requer tipo definido pelo utilizadorCapability

Espaço de nome: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Atributo reconhecido pelo compilador usado para marcar uma chamada com as capacidades de tempo de execução que requer.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Itens nomeados

### <a name="level--string"></a>Nível : [Corda](xref:microsoft.quantum.lang-ref.string)

O nome do nível de capacidade de execução exigido pelo callable.
### <a name="reason--string"></a>Razão : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma descrição do porquê da chamada requer esta capacidade de tempo de execução.

## <a name="remarks"></a>Observações

Este atributo é automaticamente adicionado aos callables pelo compilador, a menos que já exista uma instância deste atributo no callable. Não deve ser utilizado exceto em casos raros em que o compilador não infera corretamente a capacidade necessária.

Abaixo está a lista de nomes de nível de capacidade, para aumentar as capacidades ou reduzir restrições:

## `"BasicQuantumFunctionality"`

Os resultados da medição não podem ser comparados para a igualdade.

## `"BasicMeasurementFeedback"`

Os resultados da medição só podem ser comparados para a igualdade em expressões condicionais de declaração em operações. O bloco de uma declaração se-if que depende de um resultado não pode conter declarações definidas para variáveis mutáveis declaradas fora do bloco, ou declarações de devolução.

## `"FullComputation"`

Sem restrições de tempo de execução. Qualquer programa Q# pode ser executado.