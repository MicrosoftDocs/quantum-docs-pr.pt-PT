---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Decomposição Esclarou o tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: eb2aed53b4116a4ea72ee732ff46c4a10eb3d67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855511"
---
# <a name="decompositionstate-user-defined-type"></a>Decomposição Esclarou o tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Estado durante a decomposição com base em índices variáveis

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a>Itens nomeados

### <a name="perm--int"></a>Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]


### <a name="lfunctions--bigintint"></a>Funções : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int))[]


### <a name="rfunctions--bigintint"></a>Rfunctions : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int)[]



## <a name="description"></a>Descrição

O Estado detém a permutação atual e as funções atualmente geradas para portões controlados à esquerda, e portões controlados à direita.