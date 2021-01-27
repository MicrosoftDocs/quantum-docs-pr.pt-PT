---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Requer tipo definido pelo utilizadorCapability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855144"
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